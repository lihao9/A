# Android Compose 技术选型与开发规范

## 必须使用的库

- Compose UI、Material 3、Activity Compose、ViewModel Compose（基础）

- Navigation Compose

- Preferences DataStore

- Retrofit（基于 OkHttp）；序列化框架优先沿用当前模块已有的 Kotlinx Serialization、Moshi 或 Gson，不引入第二套框架。项目尚未配置时，默认使用 Kotlinx Serialization，并补齐 Retrofit Converter 与统一 Json 配置。

- 公共请求头、Debug 日志和 AES 加解密统一使用 OkHttp 拦截器实现。

- Coil 3\.4\.0（仅用于图片加载，但本架构可不使用，可省略）

## Compose UI 与预览约束

1. 页面采用 Stateful `XxxRoute` 与 Stateless `XxxScreen`/Content 分层。Route 在 NavHost 路由层获取 ViewModel、收集状态并转发事件；Screen、Content 和对话框只接收纯数据状态与语义事件，不接收 Application、Repository、ViewModel 或 NavController。Preview 直接传入示例状态和空回调，确保稳定渲染。

2. 无法在 Preview 中运行的 WebView、地图或播放器等组件，通过 `LocalInspectionMode.current` 显示稳定占位，保证其余界面正常预览。

---

## App 开发最小架构规范

本章节是新项目和新增功能的最低实现标准。既有项目按职责增量遵守，不为匹配目录、命名或技术选型进行无关迁移；未出现明确需求时，不强制引入多模块、Domain/UseCase、Room、离线优先、WorkManager 或完整 CI/CD。

### 1\. 基础架构与依赖方向

```text
Compose Route
↓
ViewModel
↓
Repository
↓
RemoteDataSource / LocalDataSource
↓
Retrofit / DataStore
```

- 依赖只能从上层指向下层，下层禁止依赖 UI。

- UI 禁止直接访问 Repository、Retrofit 或 DataStore。

- 网络 DTO 不得直接作为 UI 状态使用； ViewModel 中转换为页面需要的模型。

### 2\. 依赖管理

- 新项目或尚未配置依赖注入的项目使用手写 `AppContainer`。既有项目已使用 Hilt 或 Koin 时继续沿用，不在普通业务需求中迁移，也不并存第二套 AppContainer 注入体系。

- `MyApplication` 只负责初始化和持有 `AppContainer`。

- `AppContainer` 负责创建 Retrofit、DataStore、DataSource、Repository 及其他应用级依赖。

- 使用 AppContainer 时，ViewModel 通过构造函数接收依赖，并由统一的 `ViewModelProvider.Factory` 创建；使用既有 Hilt 或 Koin 时遵循项目现有创建方式。

- 禁止在 ViewModel 中保存或主动获取 Application、Activity、Context、NavController。

### 3\. UI 与状态管理

- 每个页面定义不可变的 `XxxUiState`，至少表达加载、内容、空数据和错误信息。

- 页面操作统一通过 `XxxAction` 或语义清晰的回调传递给 ViewModel。

- ViewModel 对外只暴露不可变 `StateFlow`，内部状态不得直接暴露给 UI 修改。

- Compose 使用 `collectAsStateWithLifecycle()` 收集页面状态。

- 页面和对话框只接收纯数据状态与事件回调，不接收 ViewModel 或 NavController。

- 业务状态由 ViewModel 管理；输入框、滚动位置、展开状态等纯 UI 状态优先留在 Compose，必要时使用 `rememberSaveable`。

- Toast、Snackbar、导航结果等行为必须避免重复消费；可恢复的结果优先建模为 UiState。

- 提交按钮和导航按钮必须防重复点击。全局 Loading 引用计数大于零时用户不可手动关闭，归零后必须正常隐藏；请求进行中不得重复提交相同操作，请求结束后必须恢复可操作状态。

```kotlin
data class XxxUiState(
    val isLoading: Boolean = false,
    val data: XxxData? = null,
    val isEmpty: Boolean = false,
    val errorMessage: String? = null
)
```

### 4\. Repository 与本地数据

- Retrofit API 调用放在 RemoteDataSource，DataStore 读写放在 LocalDataSource 或专用 PreferenceDataSource。

- Repository 负责数据源编排以及 DTO 到上层数据模型的转换，不承担 Retrofit、OkHttp 或解析异常到 `AppError` 的转换；异常统一由 `BaseViewModel.launchRequest` 处理。

- DataStore 只保存 Token、用户 ID、环境配置、功能开关等轻量键值数据。

- 复杂对象、业务列表和需要查询关系的数据禁止直接存入 Preferences DataStore；出现明确结构化缓存需求时再引入 Room。

- 退出登录时必须清除账号 Token、用户信息及账号相关本地状态。

- DataSource 对外方法必须可安全地从主线程调用；阻塞任务需要切换到合适的 Dispatcher。

### 5\. 网络、错误与认证

- 定义统一的 `ApiResult<T>`，区分成功和失败。

- 定义统一的 `AppError`，至少覆盖 HTTP 错误、业务错误、断网、超时、解析失败和未知错误。

- `BaseViewModel.launchRequest` 负责把 Retrofit、OkHttp、服务端业务错误和解析异常统一转换为 `AppError`；UI 不直接捕获异常，也不判断 HTTP 状态码或服务端错误码。

- 连接、读取和写入超时统一配置为 60 秒，禁止各接口自行设置不同默认值。

- 响应 code 为 401 或 402 时交给统一认证组件处理。认证组件最多刷新一次 Token，并发失效请求共享同一次刷新结果；刷新失败后清理登录状态并进入登录流程。刷新成功后只自动重放幂等请求，支付、下单等非幂等请求不得自动重放。

- 所有请求使用协程执行，并随对应 ViewModel 或业务作用域取消。

- 拦截器顺序固定为：公共 Header 拦截器 → 日志拦截器 → AES 加解密拦截器。

- 序列化优先沿用当前模块已有的 Kotlinx Serialization、Moshi 或 Gson；项目尚未配置时默认使用 Kotlinx Serialization。服务端字段缺失或新增时不得导致无关页面崩溃。

### 6\. Navigation Compose

- 采用单 Activity 和单 NavHost 架构，使用 `rememberNavController()` 创建 NavController。

- 所有路由集中定义，禁止在页面内部散落硬编码路由字符串。

- NavHost 路由层负责获取 ViewModel、收集状态并把纯状态及回调传给 Screen。

- Screen 不接收 NavController，只接收 `onNavigateXxx` 等导航回调。

- 页面之间只传 ID、枚举、布尔值等必要参数，禁止通过路由传递大型对象或完整 DTO。

- 必须明确启动页、登录页和主页的跳转与清栈规则，退出登录后禁止返回已登录页面。

### 7\. 网络与数据安全

- AES 实现必须统一规定算法模式、Padding、IV 或 Nonce、字符编码及密钥来源，客户端和服务端保持一致。

- 正式密钥禁止直接硬编码在源码、BuildConfig 或资源文件中；需要本地保护的密钥材料使用 Android Keystore。

- 禁止明文 HTTP；测试环境如有例外，必须通过独立的 Debug Network Security Config 配置，Release 不得继承。

- 日志拦截器仅在 Debug 构建启用。

- Debug、测试和生产环境使用独立 Base URL，禁止在业务代码中硬编码环境地址。

### 8\. 最小包结构

以下结构用于新项目或新增独立模块。既有项目只需将职责映射到现有目录，不为匹配目录名称进行无关移动或重命名。

```text
application/
    MyApplication
    AppContainer

core/
    network/
    error/
    security/

data/
    api/
    remote/
    local/
    model/
  

ui/
    navigation/
    screen/
    viewmodel/
    dialog/
    theme/
```

- `MainActivity` 放在 `ui` 包根目录。

- 网络 DTO 放在 `data.model`，Retrofit 接口放在 `data.api`。

- 通用网络、错误和安全能力分别放入 `core.network`、`core.error`、`core.security`。

- 包名按职责划分，不按“工具类”“管理器”等模糊名称集中堆放。

### 9\. 版本与构建要求

- 项目必须在 Gradle 中明确 `minSdk`、`targetSdk`、Kotlin、JDK 和 AGP 版本。

- Compose 依赖优先使用 Compose BOM 对齐版本，其余依赖统一使用 Version Catalog 管理。

- 至少区分 Debug 和 Release；存在独立测试服务时增加 Staging。

- Base URL、日志开关和调试配置通过构建环境注入，禁止散落在业务代码中。

- Release 构建启用 R8，并针对实际使用的反射序列化框架或库验证必要 Keep Rules；Kotlinx Serialization 不机械添加无关的反射 Keep 配置。

### 10\. 最低测试要求

- ViewModel：至少覆盖加载、成功、空数据、失败状态转换，以及一次性行为不会重复消费。

- Repository 与 DataSource：至少覆盖网络成功、业务失败、数据转换、异常传播和 Token 失效传播，并确认错误最终由 `BaseViewModel.launchRequest` 转换为 `AppError`。

- 认证：覆盖并发 401/402、单次 Token 刷新、刷新失败退出登录、幂等请求重放和非幂等请求不重放。

- 安全：覆盖 AES 加解密一致性、异常密文和敏感日志脱敏。

- Navigation：至少覆盖启动页以及登录页到主页的关键跳转和清栈行为。

- 测试必须使用 Fake Repository 或可控 DataSource，禁止依赖真实 Application、真实接口或正式账号。

