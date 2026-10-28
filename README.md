# jfhcs（金凤凰复制版）

2026-10-28 从 [`yql-android`](https://github.com/yinyuan1990/yql-android)（金凤凰）`4a1a53d` 复制，功能和金凤凰一样，区别：

- **applicationId**：`com.fz.yqlandroid.cs`（可与金凤凰同装；代码 namespace 仍是 `com.fz.yqlandroid`，方便两边同步改动）
- **设备号前缀**：`androidcs`，后端 / 总后台 / PC 显示 **Android-cs**
- **支持 SRT全码**（1920×1440 / 2K / 4K、原画质、流量），和健康养生一样；金凤凰从 10-28 起不支持
- **强更 / 下载**：总后台「App配置」`jfhcs` 块，下载地址 `updatesoft/jfhcs.apk`；最新版本号读 `latestVersions.jfhcs`
- App 名字仍是「金凤凰」

---

# yql-android

Android 端推流客户端，与 iOS 端 [`srs_yql`](https://github.com/yinyuan1990/srs_yql) 对齐同一套后端 API 与 SRS WebRTC 推流协议。

- **包名**：`com.fz.yqlandroid`
- **技术栈**：Kotlin · Jetpack Compose · WebRTC · Camera2
- **iOS 对照仓库**：https://github.com/yinyuan1990/srs_yql.git
- **当前阶段**：SRS 推流优先（P2P / SRT 暂缓）

## 本地路径

```
/Users/chengyuan/aiqipai/ios/sysandroid
```

## 构建

```bash
./gradlew assembleDebug
```

## 文档

| 文件 | 说明 |
| --- | --- |
| [docs/PROGRESS.md](docs/PROGRESS.md) | 开发进度、与 iOS 功能对照 |
| [docs/项目路径说明.md](docs/项目路径说明.md) | 全系统各端仓库索引 |

## 关键模块

| 文件 | 职责 |
| --- | --- |
| `manager/WebRTCManager.kt` | WebRTC 总控：采集、编码、SRS 推流、档位切换 |
| `manager/Camera2ControlCapturer.kt` | 自定义 Camera2 采集 + 硬件控制（变焦/对焦/曝光/白平衡） |
| `manager/WebSocketManager.kt` | STOMP 长连接、CONFIG_STATE 心跳 |
| `network/NetworkService.kt` | 登录、注册、推流 Token |
| `ui/screen/StreamingScreen.kt` | 预览与自动推流 |
