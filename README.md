# PUA

解锁 APP 开发最后一公里的新姿势。

[PUA（Plugin Upload App）](https://marketplace.visualstudio.com/items?itemName=cmd-studio.pua)是一个面向 Flutter 项目的 VS Code 分发扩展，目标不是再造一个“上传按钮”，而是把应用从本地构建、版本整理、渠道配置到多平台分发这一整段最后一公里流程，收敛到一个可视化、可复用、可追踪的工作台里完成。

传统发布流程里，开发者往往需要在命令行、构建脚本、各家应用市场后台和测试分发平台之间来回切换。PUA 把这些碎片化动作重新编排成一个统一入口，让发布动作更短、反馈更及时、错误更容易定位。

![PUA Overview](https://github.com/JewSaten/PUA/raw/HEAD/images/image1.png)
![PUA Publish](https://github.com/JewSaten/PUA/raw/HEAD/images/image2.jpg)
![PUA Versions](https://github.com/JewSaten/PUA/raw/HEAD/images/image3.png)

## 为什么是 PUA

- 把构建、上传、分发、版本查询集中到 VS Code 内完成
- 降低发布过程对命令行和平台后台的依赖
- 用可视化配置替代重复输入，减少人为失误
- 用任务进度、取消、失败重试提升发布可控性
- 面向多平台分发场景，不再局限于单一测试分发工具

## 核心能力

### 1. 一键构建并分发

- 支持 Flutter Android / iOS 构建
- 支持自定义版本号、构建号
- 支持自动递增构建号
- 支持自定义 Dart 入口文件
- 支持自定义构建产物输出目录
- 支持全局更新说明，并可被平台级说明覆盖

### 2. 直接上传已有安装包

- 支持上传已有 APK / IPA 文件
- 适合 CI 产物复用、补发渠道包、跳过本地构建场景

### 3. 多平台统一分发配置

当前已接入平台包括：

- 蒲公英
- 华为应用市场
- 荣耀应用市场
- 小米应用商店
- OPPO 开放平台
- 魅族应用商店
- VIVO 开放平台
- 腾讯应用宝
- App Store

### 4. 平台版本总览

- 在扩展内查看已配置平台的在架版本信息
- 快速比对版本号、构建号、发布时间、状态
- 支持直接跳转平台后台或安装页

### 5. 发布任务可观测

- 展示构建和分发的完整任务进度
- 支持上传进度反馈
- 支持任务取消
- 支持单节点失败后重试
- 支持查看构建产物与分发结果

## 适用场景

- Flutter 应用日常测试包分发
- 多安卓渠道市场同步提审或上传
- iOS / Android 版本发布前的统一出包操作
- 希望在 VS Code 内完成“构建 + 分发 + 查版本”的团队流程

## 快速开始

### 1. 安装扩展

在 VS Code 中安装 `PUA` 扩展。

### 2. 打开扩展入口

可通过以下任一方式使用：

- 侧边栏打开 `PUA`
- 快捷键 `Cmd+Shift+R` / `Ctrl+Shift+R`
- 命令面板输入 `PUA`

### 3. 配置发布参数

在扩展面板中完成：

- Flutter 构建参数
- 版本名称 / 构建号
- Dart 入口文件
- 输出目录
- 全局更新说明
- 各平台 API 凭证与发布参数

### 4. 执行发布

根据场景选择：

- `构建并分发`
- `上传已有安装包`

## 推荐工作流

1. 在 `发布设置` 中维护统一的构建参数
2. 在 `平台配置` 中启用需要参与分发的渠道
3. 先通过 `平台版本总览` 确认当前线上或测试版本状态
4. 执行 `构建并分发` 或 `上传已有安装包`
5. 根据任务结果决定是否重试失败节点或进入下一轮发布

## 设计理念

PUA 想解决的不是“如何再快一点上传一个包”，而是 APP 开发中最容易被忽视、却又最消耗注意力的最后一公里：

- 发布动作散落在不同平台
- 构建参数容易漂移
- 更新说明重复填写
- 渠道状态缺少统一视图
- 出错后很难快速恢复

所以在 1.0.0，我们把重点放在两个词上：

- `统一入口`
- `流程可控`

## 平台与凭证说明

不同平台需要各自的 API 凭证、应用标识或发布参数。请根据面板内字段提示和平台官方文档完成配置。

部分常用文档入口：

- [蒲公英 API 文档](https://www.pgyer.com/doc/view/api#paramInfo)
- [蒲公英 API 信息页面](https://www.pgyer.com/account/api)
- [华为 AppGallery Connect API](https://developer.huawei.com/consumer/cn/doc/AppGallery-connect-Guides/agcapi-getstarted-0000001111845114#section1679462873111)
- [荣耀开放服务文档](https://developer.honor.com/cn/doc/guides/101359)
- [小米开放平台文档](https://dev.mi.com/xiaomihyperos/documentation/detail?pId=1134)
- [OPPO 开放平台文档](https://open.oppomobile.com/documentation/page/info?id=10998)

## 安全说明

- 平台敏感信息通过 VS Code 扩展配置和安全存储能力进行管理
- 建议使用最小权限原则配置各平台凭证
- 发布前请确认版本号、包名、渠道配置与更新说明

## 交流与支持

如果你想交流 Flutter 分发、渠道发布、插件使用问题，欢迎扫码添加作者微信，备注 `PUA` 入群。

![添加作者微信入群](https://github.com/JewSaten/PUA/raw/HEAD/images/wechat.jpg)

如果这个插件对你有帮助，欢迎给个 [⭐️ Star](https://github.com/JewSaten/PUA) 支持一下。

## 工具使用条款

使用本工具即表示您同意以下条款：

- 自觉遵守各分发平台服务协议及 API 使用规范
- 对因不当使用本工具而产生的任何后果自行负责
- 本工具作者不对任何违规使用行为或由此产生的损失承担责任
