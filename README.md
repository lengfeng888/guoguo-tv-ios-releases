# 果果 TV iOS 客户端

这是果果 TV iOS 客户端的公开发布页。仓库只提供安装包、校验文件和说明文档，源代码维护在私有仓库中。

> **重要：当前 IPA 未签名，不能直接安装到普通 iPhone 或 iPad。** 请先使用你自己的 Apple ID 或开发者证书完成重签名，再通过 Sideloadly、AltStore、Feather 等工具安装。详细步骤见 [安装说明.md](安装说明.md)。

## 配合果果剧库使用

本客户端需要连接服务端才能浏览、搜索和播放内容。服务端安装包与完整说明请前往配套项目：

- [果果剧库公开发布仓库](https://github.com/lengfeng888/guoguo-juku-releases)

推荐使用顺序：

1. 在 [guoguo-juku-releases](https://github.com/lengfeng888/guoguo-juku-releases) 下载适合你的电脑或 NAS 的果果剧库服务端。
2. 按照该项目的 `完整说明.md` 启动服务端，并确认 `/tvbox.json` 可以正常访问。
3. 安装本仓库的果果 TV iOS 客户端，在连接页填写服务端的局域网或公网地址。
4. 确认手机与服务器网络互通，并在系统弹窗中允许 App 使用本地网络。

示例服务端地址：

```text
http://192.168.1.10:8999
http://192.168.1.10:8999/tvbox.json
```

不要填写 `127.0.0.1` 或 `localhost`，它们指向 iPhone 或 iPad 自己，而不是运行果果剧库的电脑或 NAS。

## 下载

| 版本 | 构建号 | 文件 | 安装包状态 |
| --- | --- | --- | --- |
| 1.0.3 | 4 | [GuoGuoTV-1.0.3-4-unsigned.ipa](GuoGuoTV-1.0.3-4-unsigned.ipa) | 当前版本，完全未签名 |
| 1.0.2 | 3 | [GuoGuoTV-1.0.2-3-unsigned.ipa](GuoGuoTV-1.0.2-3-unsigned.ipa) | 历史版本，完全未签名 |
| 1.0.1 | 2 | [GuoGuoTV-1.0.1-2-unsigned.ipa](GuoGuoTV-1.0.1-2-unsigned.ipa) | 历史版本，完全未签名 |
| 1.0 | 1 | [GuoGuoTV-1.0-1-unsigned.ipa](GuoGuoTV-1.0-1-unsigned.ipa) | 历史版本，完全未签名 |

- 当前文件大小：1,014,561 字节（约 0.97 MiB）
- 当前 SHA-256：`7c8fba0583ffebbd59e28d2fb6d402e861e59048a14076e6a1c00e7d9d4033c6`
- 校验文件：[SHA256SUMS.txt](SHA256SUMS.txt)

本次 `1.0.3 (4)` 更新重点：

- 优化播放器加载动画位置和竖屏进度时间布局。
- 修复竖屏倍速滚轮的中心定位和拖动选择。
- 弹幕轨道重新分配，滚动弹幕最多显示 3 行，固定弹幕各 1 行。
- 横竖屏切换时强制重建弹幕布局，避免旋转后弹幕消失。

## 构建信息

| 项目 | 内容 |
| --- | --- |
| App 名称 | 果果TV |
| Bundle Identifier | `com.guoguo.tvbox` |
| 版本 | `1.0.3 (4)` |
| 源码提交 | `c83d99a` |
| 构建日期 | 2026-10-04 |
| 构建工具 | Xcode 27.0（27A266a） |
| CPU 架构 | `arm64` |
| 最低系统 | iOS 16.0 |
| 支持设备 | iPhone、iPad |
| 签名状态 | 未签名，无 Provisioning Profile |
| 音频后台模式 | 已开启 |

## 功能概览

- 连接果果剧库或兼容 TVBox 的服务端。
- 支持 TVBox JSON 配置、JSON CMS 和 XML CMS 接口。
- 支持多线路、剧集分页、搜索来源筛选、收藏和观看历史。
- 基于 `AVPlayer` 的播放器：选集、自动连播、续播、缓存进度、倍速和画面比例。
- 支持横竖屏、画中画、播放手势、亮度/音量调节和长按倍速。
- 支持 TVBox 弹幕搜索、XML 解析、渲染和开关。

## 使用前需要准备

1. 从 [果果剧库公开发布仓库](https://github.com/lengfeng888/guoguo-juku-releases) 获取并启动服务端。
2. 手机和服务器处于可以互相访问的网络中。
3. 一个用于重签名的 Apple ID 或 Apple Developer 证书。
4. 安装后首次连接局域网服务端时，允许 App 使用本地网络。

客户端不包含影视资源。服务端地址、账号、接口和播放内容均由使用者自行提供。

## 校验下载文件

macOS：

```sh
shasum -a 256 GuoGuoTV-1.0.3-4-unsigned.ipa
```

Linux：

```sh
sha256sum GuoGuoTV-1.0.3-4-unsigned.ipa
```

正确结果：

```text
7c8fba0583ffebbd59e28d2fb6d402e861e59048a14076e6a1c00e7d9d4033c6
```

## 安装与风险说明

- 本仓库不分发任何证书、描述文件、Apple ID、设备 UDID 或签名后的安装包。
- 未签名 IPA 只适合自行重签名和自用测试，不适合直接提交 App Store。
- 使用免费 Apple ID 签名通常需要每 7 天重新签名，且可能有同时安装的 App 数量限制。
- 第三方重签名工具由对应项目维护，请从其官方渠道下载并自行评估风险。
- TVBox 服务端、第三方站点、弹幕和播放内容的可用性及版权责任由使用者自行确认。
- 当前 `Info.plist` 允许明文 HTTP，以兼容局域网 TVBox 服务端；能使用 HTTPS 时应优先使用 HTTPS。
