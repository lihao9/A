# 阿根廷 RayoYa 页面用途说明

> 来源：Figma 文件「阿根廷RayoYa」（page 13:24225，共 146 个顶层画板）+ `AR_Android需求文档.md`（2026-10-03 版）。  
> 格式参照飞书《页面用途说明》；在「页面名称 / Figma / 类型 / 页面用途」四列基础上增加「对应需求」列，方便回溯需求文档。  
> 画板基准链接：[阿根廷RayoYa](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29361)（node-id 13-29361「启动页」）。  
> 同一职责的多状态画板合并在同一行，用 ` · ` 分隔；类型区分页面 / 弹窗 / 弹层 / 对话框 / 引导页 / 组件态 / 素材。

## 目录

- [A 启动与合规](#page-a)
- [B 登录注册与账号安全](#page-b)
- [C 身份认证 KYC](#page-c)
- [D 首页与订单助手](#page-d)
- [E 借款申请](#page-e)
- [F 订单与还款](#page-f)
- [G 个人中心](#page-g)
- [H 全局页面与组件](#page-h)
- [检查一：Figma 画板覆盖情况](#page-check-1)
  - [另一处画布「丢失的页面」里的重名画板（需确认）](#page-check-1-lost)
- [检查二：需求多状态覆盖检查](#page-check-2)
  - [逐需求覆盖结论](#page-check-2-cover)

---

---

<a id="page-a"></a>
# A 启动与合规

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **A-01 启动页** | AND-001 | [启动页](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29361) | 页面 | 应用冷启动时展示品牌，约 1.5 秒后按合规进度分流。 |
| **A-02 隐私政策页** | COMM-001 | [隐私政策 【文案参考需求翻译】](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32235) | 页面 | 展示隐私政策内容，用户同意或不同意后进入权限说明页。 |
| **A-03 授权声明页（权限说明页）** | COMM-001 | [授权声明【文案参考需求翻译】](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32279) | 页面 | 说明短信、定位、相机等权限用途，两道同意均通过后写「全部同意」。 |
| **A-04 授权声明补偿页** | COMM-001 | [授权声明补偿【配图待更换】](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32559) | 页面 | 首页敏感入口触发合规补走时，重新走隐私与权限说明。 |
| **A-05 未全部授权再次进入首页提示** | COMM-001 / AND-017 | [未全部授权再次进入首页提示](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32635) | 弹窗 | 未全部同意时进入首页、或点击敏感入口时的引导提示。 |
| **A-06 数据上报说明弹窗** | AND-003 | [数据上报弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32655) | 弹窗 | 风控上报前说明采集内容，用户确认后申请权限并上报。 |
| **A-07 数据上报风险提示** | AND-003 | [数据上报-风险提示](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32176) | 弹窗 | 上报链路的风险提示文案。 |
| **A-08 版本更新弹窗（强制）** | AND-008 | [升级弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29500) | 弹窗 | 强更：不可关闭，引导前往商店更新。 |
| **A-09 版本更新弹窗（非强制）** | AND-008 | [升级弹窗——非强制](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29527) | 弹窗 | 弱更：可关闭，关闭后继续首页流程。 |
| **A-10 公告弹窗** | AND-017 | [公告弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29518) | 弹窗 | 首页接口返回公告时展示，关闭后继续首页。 |

<a id="page-b"></a>
# B 登录注册与账号安全

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **B-01 输入手机号页（未输入 / 已输入）** | AND-004 | [输入手机号-未输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31729) · [输入手机号-已输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31796) | 页面 | 录入 9 位手机号，校验通过后进入验证码。 |
| **B-02 注册验证码-倒计时** | AND-004 | [注册 验证码 倒计时](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29564) | 页面 | 验证码发出后的 30 秒倒计时态。 |
| **B-03 注册验证码-重新发送** | AND-004 | [注册 验证码 重新发送](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31877) | 页面 | 倒计时结束后的可重发态。 |
| **B-04 注册验证码-通过 / 错误提示** | AND-004 | [注册 验证码 通过/错误提示](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31945) | 页面 | 验证码校验成功与失败两种提示态。 |
| **B-05 注册验证码-获取语音验证码后** | AND-004 | [注册 获取语音验证码后](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32015) | 页面 | 用户选择语音验证码后的页面态。 |
| **B-06 注册图像验证码** | AND-004 | [注册 图像验证码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32087) | 页面 | 发码前需要图形验证码时的输入页。 |
| **B-07 选择收取验证码方式** | AND-004 | [选择收取验证码方式](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32128) | 对话框 | 在短信 / WhatsApp / 语音之间选择验证码渠道。 |
| **B-08 注册设置密码（未输入 / 已输入）** | AND-004 | [注册 设置密码 未输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30985) · [注册 设置密码 已输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31538) | 页面 | 首次注册时设置登录密码。 |
| **B-09 登录-登录密码（未输入 / 已输入）** | AND-004 | [登录-登录密码 未输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31402) · [登录-登录密码 已输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31470) | 页面 | 已设密码用户用登录密码登录。 |
| **B-10 重置登录密码（未输入 / 已输入）** | AND-004 | [重置登录密码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30547) · [重置登录密码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30648) · [重置登录密码-已输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30748) | 页面 | 忘记密码时重置登录密码。 |
| **B-11 重置登录密码成功** | AND-004 | [重置登录密码成功](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30851) | 页面 | 重置成功后的结果页。 |
| **B-12 退出输入手机号页面挽留弹窗** | AND-004 | [退出输入手机号页面挽留弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32194) | 弹窗 | 用户中途退出手机号页时的挽留确认。 |
| **B-13 更换设备验证** | AND-005 | [更换设备验证](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29636) | 页面 | 检测到换设备时要求验证身份。 |
| **B-14 更换设备验证-输验证码** | AND-005 | [更换设备验证-输验证码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29675) | 页面 | 换设备验证的短信验证码输入态。 |
| **B-15 更换设备验证-图形验证码** | AND-005 | [更换设备验证-图形验证码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33027) | 页面 | 换设备验证的图形验证码输入态。 |
| **B-16 账号风险提示** | AND-005 | [账号风险提示](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31623) | 弹窗 | 账号存在风险或受限时的提示。 |
| **B-17 登录（账号已删除）提示** | AND-037 | [登录(账号被删除了）时弹出](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31705) | 弹窗 | 已注销账号再次登录时的提示与改号入口。 |
| **B-18 安全验证（未输入 / 已输入）** | AND-037 | [安全验证](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31068) · [安全验证——已输入](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31220) | 页面 | 注销前的身份安全验证。 |
| **B-19 注销-安全验证** | AND-037 | [注销- 安全验证](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31151) | 页面 | 注销流程专用安全验证页。 |
| **B-20 账号删除成功** | AND-037 | [账号删除成功](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31655) | 页面 | 注销完成后的结果页。 |
| **B-21 重置交易密码** | AND-036 | [重置交易密码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30869) | 页面 | 账户安全内重置交易密码。 |
| **B-22 重置交易密码成功** | AND-036 | [重置交易密码成功](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30860) | 页面 | 重置交易密码成功的结果页。 |

<a id="page-c"></a>
# C 身份认证 KYC

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **C-01 授信-基本信息** | AND-012 | [授信-基本信息](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-25359) | 页面 |  OCR 关闭时的个人资料填写首屏。 |
| **C-02 授信-基本信息 其他状态** | AND-012 | [授信-基本信息 其他状态](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-25567) | 页面 | 个人资料页的其它字段/错误状态。 |
| **C-03 授信-基本信息 确认信息** | AND-012 | [授信-基本信息 确认信息](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27144) | 页面 | 提交前的资料确认态。 |
| **C-04 授信-基本信息 生日选择** | AND-012 | [授信-基本信息 生日选择](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27207) | 选择器 | 生日日期选择弹层。 |
| **C-05 授信-基本信息 单选** | AND-012 | [授信-基本信息 单选](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27211) | 选择器 | 性别等单选控件展开态。 |
| **C-06 授信-基本信息 日单选** | AND-012 | [授信-基本信息 日单选](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27637) | 选择器 | 发薪日等日期单选控件。 |
| **C-07 授信-工作信息** | AND-012 | [授信-工作信息](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-25771) | 页面 | 工作与居住信息填写。 |
| **C-08 亲密联系人** | AND-013 | [亲密联系人](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-26043) | 页面 | 填写两名紧急联系人及其关系。 |
| **C-09 授信-证件信息** | AND-014 | [授信-证件信息](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-26208) | 页面 | 身份证正反面拍摄/相册与 OCR 回填表单。 |
| **C-10 授信-证件信息已上传** | AND-014 | [授信-证件信息已上传](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-26353) | 页面 | 证件已上传成功后的回填态。 |
| **C-11 授信-照片加载失败** | AND-014 | [授信-照片加载失败](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-26599) | 页面 | 证件图片加载失败的错误态。 |
| **C-12 DNI 示例图** | AND-014 | [DNI](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27730) · [DNI](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27750) | 素材 | 身份证正反面示例图素材。 |
| **C-13 授信-拍照引导正面** | AND-014 | [授信-拍照引导正面](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27381) | 引导页 | 拍摄身份证正面的取景引导。 |
| **C-14 授信-拍照引导反面** | AND-014 | [授信-拍照引导反面](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27439) | 引导页 | 拍摄身份证反面的取景引导。 |
| **C-15 拍照前** | AND-014 | [拍照前](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28699) | 相机页 | 相机取流前的准备态（横屏）。 |
| **C-16 拍照后** | AND-014 | [拍照后](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28717) | 相机页 | 拍摄完成后的确认/重拍态（横屏）。 |
| **C-17 活体-面对镜头** | AND-016 | [活体-面对镜头](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28737) | 引导页 | 活体第一步：正脸入镜。 |
| **C-18 活体-保持微笑** | AND-016 | [活体-保持微笑](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28814) | 引导页 | 活体随机动作之一。 |
| **C-19 活体-左右摇头** | AND-016 | [活体-左右摇头](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28891) | 引导页 | 活体随机动作之一。 |
| **C-20 授信最后一步-添加银行卡** | AND-015 | [授信最后一步--添加银行卡](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-26847) | 页面 | 授信链尾部的收款账户录入。 |
| **C-21 授信-风险评估loading** | AND-011 / AND-018 | [授信-风险评估loading](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27088) | 页面 | 授信提交后的风险评估/额度计算等待态。 |
| **C-22 授信-失败** | AND-011 | [授信-失败](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27022) | 页面 | 授信失败的结果页。 |
| **C-23 授信-挽留弹窗** | AND-011 | [授信-挽留弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27302) | 弹窗 | 授信中途返回时的挽留。 |
| **C-24 授信-挽留弹窗-其他** | AND-011 | [授信-挽留弹窗-其他](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27497) | 弹窗 | 授信挽留的其它文案/状态。 |
| **C-25 弹挽留弹窗“重要提醒”** | AND-011 | [弹挽留弹窗“重要提醒”](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-26958) | 弹窗 | 重要提醒样式的挽留弹窗。 |
| **C-26 不需要钱-确认借款** | AND-011 | [不需要钱-确认借款](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-26990) | 弹窗 | 用户表示不需要资金时的确认弹窗。 |
| **C-27 提示用户需要补充 OCR 资料** | AND-014 / AND-017 | [弹窗提示用户需要补充OCR资料](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33067) | 弹窗 | 首页返回后提示补充证件资料。 |

<a id="page-d"></a>
# D 首页与订单助手

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **D-01 首页 / 首页-默认** | AND-017 | [首页](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27770) · [首页-默认](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27854) | 页面 | 登录后的首页默认形态（虚拟首页/已获额按状态切换）。 |
| **D-02 首页-不可用-账单** | AND-017 | [首页-不可用-账单](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29710) | 页面 | 产品不可用且带账单卡的首页形态。 |
| **D-03 首页-账单 处理中** | AND-017 | [首页-账单 处理中](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29832) | 页面 | 订单处理中的账单卡态。 |
| **D-04 首页-账单失败** | AND-017 | [首页-账单失败](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29954) | 页面 | 订单失败的账单卡态。 |
| **D-05 首页-账单正常待还** | AND-017 | [首页-账单正常待还](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27962) | 页面 | 正常待还的账单卡态。 |
| **D-06 首页-账单逾期** | AND-017 | [首页-账单逾期](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30058) | 页面 | 逾期的账单卡态。 |
| **D-07 账单状态 1（多状态合集）** | AND-017 | [账单状态1](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32332) | 页面 | T-1 明天到期 / T+0 今天到期等多状态对照。 |
| **D-08 账单状态 2（多状态合集）** | AND-017 | [账单状态2](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32492) | 页面 | 一期逾期、一期正常的组合状态。 |

<a id="page-e"></a>
# E 借款申请

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **E-01 借款确认（多期-收起）** | AND-021 | [借款确认-多期-收起](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28118) | 页面 | 手动申请的额度确认页默认态。 |
| **E-02 【自动提交】借款确认-多期-收起** | AND-023 | [【自动提交】借款确认-多期-收起](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28249) | 页面 | 自动提单进行中的确认页（收起）。 |
| **E-03 【自动提交】借款确认-多期-展开** | AND-023 | [【自动提交】借款确认-多期-展开](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28399) | 页面 | 自动提单进行中的确认页（展开）。 |
| **E-04 选择银行卡列表** | AND-021 / AND-033 | [选择银行卡列表](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28558) | 对话框 | 确认页内选择收款账户。 |
| **E-05 选择银行卡列表-空** | AND-021 / AND-033 | [选择银行卡列表-空](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28618) | 对话框 | 无可用账户时的空态与新增入口。 |
| **E-06 选择银行卡类型** | AND-015 / AND-033 | [选择银行卡类型](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-27575) | 对话框 | 选择 CBU / CVU / Alias 等账户类型。 |
| **E-07 首次设置交易密码** | AND-021 / AND-022 | [首次设置交易密码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28650) | 弹层 | 首次借款时设置交易密码。 |
| **E-08 验证交易密码** | AND-021 / AND-022 | [验证交易密码](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-28969) | 弹层 | 提交前校验交易密码。 |
| **E-09 借款处理中** | AND-024 | [借款处理中](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29008) | 页面 | 提交成功后的处理中结果页。 |
| **E-10 借款失败** | AND-024 | [借款失败](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29074) | 页面 | 下单失败的结果页。 |
| **E-11 好评引导** | AND-024 | [好评引导](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29548) | 弹窗 | 首贷满足条件时的应用内评价引导。 |

<a id="page-f"></a>
# F 订单与还款

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **F-01 账单（列表）** | AND-032 | [账单](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34109) | 页面 | 我的 → 借款历史（二级页）的订单列表。 |
| **F-02 账单列表-空** | AND-032 | [账单列表-空](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34296) | 页面 | 无订单时的空态。 |
| **F-03 还款历史** | AND-028 | [还款历史](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34694) · [还款历史](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34776) | 页面 | 历史还款记录列表。 |
| **F-04 还款历史-空** | AND-028 | [还款历史 空](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34639) | 页面 | 无还款记录时的空态。 |
| **F-05 正常待还** | AND-027 | [正常待还](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33110) | 页面 | 单期正常待还的订单详情。 |
| **F-06 逾期待还** | AND-027 | [逾期待还](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33991) | 页面 | 逾期待还的订单详情。 |
| **F-07 正常结清** | AND-027 | [正常结清](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33226) | 页面 | 正常结清的订单详情。 |
| **F-08 逾期结清** | AND-027 | [逾期结清](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33344) | 页面 | 逾期后结清的订单详情。 |
| **F-09 多期-正常待还** | AND-027 | [多期-正常待还](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33466) | 页面 | 多期订单全部正常待还。 |
| **F-10 多期-待还-部分结清** | AND-027 | [多期-待还-部分结清](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33582) | 页面 | 部分期次已结清、其余待还。 |
| **F-11 多期-全部正常结清** | AND-027 | [多期-全部正常结清](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33700) | 页面 | 多期全部结清。 |
| **F-12 多期-1 期逾期** | AND-027 | [多期-1逾期](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33850) | 页面 | 多期中一期逾期。 |
| **F-13 多期-1 期逾期还清** | AND-027 | [多期-1逾期还清](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34477) | 页面 | 逾期期次已还清的状态。 |
| **F-14 还款-确认页-转账（多渠道）** | AND-028 / AND-030 | [还款-确认页-转账-默认选择渠道1](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34872) · [还款-确认页-转账-默认选择渠道1](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35010) · [还款-确认页-转账-默认选择渠道1](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35148) · [还款-确认页-转账-默认选择渠道1](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35286) · [还款-确认页-转账-默认选择渠道1](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35479) · [还款-确认页-转账-默认选择渠道1](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35611) | 页面 | 转账/DEBIN 等支付渠道的还款确认与提交。 |
| **F-15 点击 Cómo pagar con DEBIN 的弹窗** | AND-030 | [点击Cómo pagar con DEBIN的弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35433) | 弹窗 | DEBIN 支付方式说明弹窗。 |
| **F-16 点击 DEBIN 的问号弹窗** | AND-030 | [点击DEBIN的问号弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35869) | 弹窗 | DEBIN 字段的说明弹窗。 |
| **F-17 H5 还款落地页** | AND-030 | [H5还款落地页](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-35751) | 页面 | 第三方支付渠道的 H5 容器页。 |
| **F-18 还款处理中** | AND-028 | [还款处理中](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34351) | 页面 | 还款提交后的处理中状态。 |
| **F-19 还款失败** | AND-028 | [还款失败](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-34414) | 页面 | 还款失败的结果页。 |

<a id="page-g"></a>
# G 个人中心

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **G-01 个人中心（我的）** | AND-032 | [个人中心](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30216) | 页面 | 查看身份信息、待还金额与功能菜单。 |
| **G-02 银行卡** | AND-033 | [银行卡](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32679) | 页面 | 收款账户列表。 |
| **G-03 银行卡-空** | AND-033 | [银行卡-空](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32896) | 页面 | 无账户时的空态。 |
| **G-04 添加银行卡** | AND-033 | [添加银行卡](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32746) · [添加银行卡](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29140) | 对话框 | 新增收款账户。 |
| **G-05 添加银行卡-填写** | AND-033 | [添加银行卡-填写](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29222) | 对话框 | 新增账户的填表态。 |
| **G-06 添加成功** | AND-033 | [添加成功](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32828) | 对话框 | 新增账户成功态。 |
| **G-07 删除银行卡确认弹窗** | AND-033 | [删除银行卡确认弹窗](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32946) | 弹窗 | 删除账户前的二次确认。 |
| **G-08 账户安全** | AND-036 | [账户安全](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-32958) | 页面 | 登录/交易密码等安全入口。 |
| **G-09 退出登录** | AND-036 | [退出登录](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-33015) | 弹窗 | 退出登录的二次确认。 |
| **G-10 意见反馈** | AND-034 | [意见反馈](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30435) | 页面 | 选择问题类型并提交反馈。 |
| **G-11 意见反馈-其他** | AND-034 | [意见反馈-其他](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-25225) | 页面 | 问题类型选「其它」时的补充说明态。 |
| **G-12 联系我们** | AND-010 | [联系我们](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-31303) | 页面 | 展示 WhatsApp / 电话 / 邮箱客服渠道。 |
| **G-13 FAQ** | AND-038 / AND-010 | [FAQ](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-30373) | 页面 | 常见问题 H5 / 列表页。 |

<a id="page-h"></a>
# H 全局页面与组件

| 页面名称 | 对应需求 | Figma | 类型 | 页面用途 |
| --- | --- | --- | --- | --- |
| **H-01 #toast** | AND-006 | [#toast](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29378) | 组件态 | 全局 Toast 样式与位置规范。 |
| **H-02 loading** | AND-006 | [loading](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29414) | 组件态 | 全局 Loading 样式。 |
| **H-03 #网络错误** | AND-007 | [#网络错误](https://www.figma.com/design/r6L7vX3RIcw6sqH5NRfP00/%E9%98%BF%E6%A0%B9%E5%BB%B7RayoYa?node-id=13-29437) | 页面/组件态 | 网络异常时的页面错误态与重试入口。 |


---

<a id="page-check-1"></a>
## 检查一：Figma 画板覆盖情况

**页面级画板 128 个，已全部纳入本文档，无遗漏。** 另有 18 个非页面画板未纳入（下表），以及 4 个非 FRAME 顶层节点（一张位图、一段文本、两个切图矩形）不计入页面。

| # | node-id | 画板名 | 未纳入原因 |
| --- | --- | --- | --- |
| 1 | `13-24267` | 基础样式 | 设计规范板，非页面 |
| 2 | `13-24811` | 组件 | 组件盘，非页面 |
| 3 | `13-24377` | 图标 | 图标盘，非页面 |
| 4 | `13-29341` | #icon图标 | 图标盘，非页面 |
| 5 | `13-25220` | 授信流程 | 流程图，非页面 |
| 6 | `13-25223` | 借款流程 | 流程图，非页面 |
| 7 | `13-29312` | 容器 3795 | 按钮素材片段 |
| 8 | `13-29316` | 容器 3399 | 费用行素材片段 |
| 9 | `13-29320` | title | 表单标题素材片段 |
| 10 | `13-29324` | title | 表单标题素材片段 |
| 11 | `13-29331` | 授权 | 画布分区标签 |
| 12 | `13-29333` | 授权 | 画布分区标签 |
| 13 | `13-29335` | 授权 | 画布分区标签 |
| 14 | `13-29337` | 首页 | 画布分区容器（590 宽，非手机页面） |
| 15 | `13-29339` | 我的 | 画布分区容器（590 宽，非手机页面） |
| 16 | `13-33104` | 容器 3829 | 倒计时素材片段 |
| 17 | `13-33106` | 账单 | 画布分区容器（590 宽，非手机页面） |
| 18 | `13-33108` | 还款 | 画布分区容器（590 宽，非手机页面） |

- 未纳入的 18 个均非手机页面：设计规范板、组件盘、图标盘、流程图、画布分区标签/容器、零散素材片段。
- 需要说明：`授权`、`首页`、`我的`、`账单`、`还款` 这 5 个名字有重复——宽度 590 的是**画布分区容器**（已排除），同名的 375 宽画板才是真页面（已纳入）。

<a id="page-check-1-lost"></a>
### 另一处画布「丢失的页面」里的重名画板（需确认）

Figma 文件除主画布「阿根廷RayoYa」外，还有一个画布 **「丢失的页面」（page 27:4618）**，里面有 3 个与主画布重名的画板：

| # | node-id | 画板名 | 主画布对应画板 | 处理 |
| --- | --- | --- | --- | --- |
| 1 | `27-4619` | 隐私政策 【文案参考需求翻译】 | `13-32235`（A-02） | 未纳入，疑似旧版副本，需确认以哪一版为准 |
| 2 | `27-4703` | 授权声明【文案参考需求翻译】 | `13-32279`（A-03） | 未纳入，疑似旧版副本，需确认以哪一版为准 |
| 3 | `27-4860` | 数据上报弹窗 | `13-32655`（A-06） | 未纳入，疑似旧版副本，需确认以哪一版为准 |

> 结论：这 3 个画板与主画布同名同职责，本次按主画布版本收录；如果实际实现稿是「丢失的页面」里的版本，请指出，我替换 A-02 / A-03 / A-06 的链接。

<a id="page-check-2"></a>
## 检查二：需求多状态覆盖检查

按需求文档的「页面及交互」逐条比对 Figma 画板，发现以下状态**有需求但无对应画板**（需设计补稿或确认可复用）：

| # | 需求 | 需求描述的状态 / 页面 | Figma 现状 | 结论 |
| --- | --- | --- | --- | --- |
| 1 | COMM-002 / AND-022 | 权限拒绝说明弹层 `H-DIALOG-PERM-DENIED`（含去设置入口） | 无同名画板 | **缺稿**：权限被拒后的唯一兜底弹层 |
| 2 | AND-003 | 35 秒上报进度弹层 `H-DIALOG-REPORT-PROGRESS` | 只有数据上报说明弹窗、风险提示 | **缺稿**：上报等待中的进度弹层 |
| 3 | AND-006 | 按钮 Loading、字段下错误、普通必填模板 | 只有全局 loading 与 #toast | **缺稿**：表单错误/按钮态未出稿 |
| 4 | AND-007 | 页面错误态 + 重试按钮 + 下拉刷新 | 只有 #网络错误 | 待确认：重试/下拉刷新是否复用 #网络错误 |
| 5 | AND-012 | 地址选择（省 / 市） | 只有生日、性别、发薪日选择器 | **缺稿**：地址选择器未出稿 |
| 6 | AND-013 | 联系人关系选择、联系人卡片错误态 | 只有联系人页主稿 | 待确认：关系选择与错误态是否复用主稿 |
| 7 | AND-014 | 相册选择弹框、图片预览、重拍态 | 有证件页、已上传、加载失败、拍照前/后 | **缺稿**：相册选择与图片预览未出稿 |
| 8 | AND-016 | 活体重试与失败态 | 只有面对镜头 / 保持微笑 / 左右摇头 | **缺稿**：活体失败与重试态未出稿 |
| 9 | AND-018 | 额度计算等待态（授信完成后） | 有授信-风险评估 loading | 待确认：是否与风险评估 loading 复用同一稿 |
| 10 | AND-017 / AND-020 | 首页产品选择（多产品卡、期限横排、金额滑动）/ 退出挽留 | 首页画板已体现产品区 | 退出挽留弹层仍缺稿 |
| 11 | AND-020 / AND-023 | 取消自动借款 / 取消倒计时弹层 | 只有自动提交确认页收起/展开 | **缺稿**：取消确认弹层未出稿 |
| 12 | AND-024 | 提交中按钮态、成功提示 | 有处理中页、失败页、好评引导 | 待确认：按钮提交中态是否由组件状态覆盖 |
| 13 | AND-027 | 期次勾选框与合计金额的勾选中间态（账单详情二级页内） | 有多期-待还-部分结清 | 待确认：勾选交互态未单独出稿 |
| 14 | AND-036 | 设置页、清除缓存确认弹窗 | 只有账户安全、退出登录、重置交易密码 | **缺稿**：设置页与清除缓存确认未出稿 |
| 15 | AND-038 | 关于我们页面 | 只有 FAQ | **缺稿**：关于我们未出稿 |

<a id="page-check-2-cover"></a>
### 逐需求覆盖结论

| 需求 | 画板覆盖 | 需求 | 画板覆盖 |
| --- | --- | --- | --- |
| COMM-001 | ✅ A-02/A-03/A-04 | AND-021 | ✅ E-01/E-04/E-05/E-07/E-08 |
| AND-001 | ✅ A-01 | AND-022 | ⚠️ 缺权限拒绝弹层 |
| COMM-002 | ⚠️ 缺权限拒绝弹层 | AND-023 | ⚠️ 缺取消倒计时弹层 |
| AND-003 | ⚠️ 缺上报进度弹层 | AND-024 | ✅ E-09/E-10/E-11 |
| AND-004 | ✅ B-01~B-12 | AND-025 | ✅ F-01~F-04 |
| AND-005 | ✅ B-13~B-16 | AND-026 | ⚠️ 勾选中间态待确认 |
| AND-006 | ⚠️ 缺表单错误态 | AND-027 | ✅ F-05~F-13 |
| AND-007 | ⚠️ 重试态待确认 | AND-028 | ✅ F-14/F-18/F-19 |
| AND-008 | ✅ A-08/A-09 | AND-030 | ✅ F-14~F-17 |
| AND-010 | ✅ G-12 | AND-032 | ✅ G-01 |
| AND-011 | ✅ C-21~C-26 | AND-033 | ✅ G-02~G-07 |
| AND-012 | ⚠️ 缺地址选择 | AND-034 | ✅ G-10/G-11 |
| AND-013 | ⚠️ 关系/错误态待确认 | AND-036 | ⚠️ 缺设置页与清缓存 |
| AND-014 | ⚠️ 缺相册/预览 | AND-037 | ✅ B-17~B-20 |
| AND-015 | ✅ C-20/E-06 | AND-038 | ⚠️ 缺关于我们 |
| AND-016 | ⚠️ 缺失败/重试态 | AND-041 | — 无用户可见页面 |
| AND-017 | ✅ D-01~D-08/A-05/A-10 | AND-018 | ⚠️ 等待态待确认 |
| AND-020 | ❌ 整页缺稿 | — | — |

