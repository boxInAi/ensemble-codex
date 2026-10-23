# 协奏 · Ensemble

**在 Codex 中管理你的 AI 团队。**

Windows 试用版 · 当前版本 **v2.3.16**

[下载安装包](https://github.com/tomlww/ensemble-codex/releases/tag/v2.3.16) · [反馈问题](https://github.com/tomlww/ensemble-codex/issues)

## 能做什么

- 用头像和成员列表进入各自的 Codex 聊天，保留原聊天记录。
- 新增、修改、移除成员，自定义名称、职责和头像。
- 默认提供 **18 张宠物头像**；上传头像作为独立文件保存在本机。
- 支持图片选择、粘贴和拖入，以及可用模型、推理强度和权限选择。
- 显示聊天摘要和工作状态，支持原聊天与插件之间的写入权交接。

成员拥有独立聊天。跨成员协作需要明确分配任务；当前版本不提供项目群聊、@多成员自动调度或完整文件预览器。部分模型与权限设置受原聊天持有状态限制。

## 安装

1. 准备 **Windows、已安装并登录的 Codex、Node.js 24+、Python 和 Pillow（支持 JPEG/WebP）**。
2. 在 [Releases](https://github.com/tomlww/ensemble-codex/releases/tag/v2.3.16) 的 **Assets** 下载 `ensemble-2.3.16-windows.zip`。不要下载 GitHub 自动生成的 `Source code` 压缩包；它不包含可安装的插件目录。
3. 解压到长期保留的文件夹，在该文件夹打开 PowerShell，运行：

   ```powershell
   .\Install.ps1
   ```

   安装脚本检查依赖并注册本地插件，不自动安装依赖或修改系统权限。若脚本策略限制运行，可在已配置 Codex CLI 的终端中执行等价命令：

   ```powershell
   codex plugin marketplace add . --json
   codex plugin add engineering-team-panel@engineering-team-local --json
   ```

4. 重新打开 Codex，打开 **协奏**。第一次点击 **创建我的团队**，会在你的账户建立 **统筹 + 12 位工程师，共 13 个独立聊天**。初始化不会发送模型消息；之后可自行增删成员。

这是供安装试用的发行仓库，插件运行文件包含在 Release 安装包中；尚未上架官方公共插件目录。

## 数据保存在你自己的电脑

- 默认目录：`%LOCALAPPDATA%\OpenAI\EngineeringTeam`。
- 新安装带有 13 位成员模板和 18 张默认头像，**不包含作者的聊天、成员自定义资料、账户凭据或上传图片**。
- 头像和消息图片存放在独立静态资源文件夹中，不内嵌到页面。
- 同名插件升级保留本机成员、头像与聊天映射。删除面板成员不会删除 Codex 原聊天。

请勿将自己的用户数据目录提交到仓库或反馈附件。

## 试用与反馈

目前已验收 Windows 本地安装流程；macOS/Linux 尚未验收。欢迎通过 Issues 提交：版本号、Windows/Codex 版本、复现步骤、预期行为和实际行为。分享截图前请遮盖私人聊天、文件路径和账户信息。

安装包附有更详细的静态资源与升级说明。Release 同时提供 SHA-256 校验文件。
