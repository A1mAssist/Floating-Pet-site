# 技术可行性与部署说明

## 系统结构

```text
Windows Electron 客户端
  主进程：透明窗口、托盘、单实例、生命周期、媒体资源回收
  Renderer：桌宠、Dock、状态条、设置、协助卡、任务、便签、记忆、专注计时
  Preload：白名单 IPC 和安全桥接
        |
Python 模型适配服务
  Chat：文字、JPEG、短 WAV
  Realtime：16 kHz 输入、JPEG 帧、增量文字、24 kHz 输出
        |
MiniCPM-o 模型服务 / 昇腾运行环境
```

## 可行性依据

1. Windows 客户端可以独立运行，桌宠窗口和本地业务状态不依赖模型服务。
2. Chat 与 Realtime 被收敛到独立 Python 服务，客户端不需要知道模型服务的内部实现。
3. 输入来源有独立开关，暂停和结束操作会停止媒体轨道并关闭实时连接。
4. Fake Adapter 允许在无模型服务时复现主要用户流程，降低评审环境部署成本。
5. OpenHarmony 路线复用 Renderer，通过 ArkWeb/ArkTS 继续承载同一产品逻辑。

## 运行入口

### Windows Demo

从 [GitHub Release](https://github.com/A1mAssist/Floating-Pet-site/releases/tag/windows-demo-0.1.0) 下载便携版 EXE，解压或直接运行。该构建用于评审体验，默认静音。

### Web Demo

打开 [floating-pet-web-demo.vercel.app](https://floating-pet-web-demo.vercel.app/)。在线版使用浏览器本地 Fake Adapter，不请求麦克风、摄像头或屏幕权限，不连接模型服务。

### 源码运行

```powershell
Set-Location .\desktop
npm ci
npm run start:fake
```

接入真实服务时，按源码仓库 `desktop/README.md` 和 `service/` 目录的协议与部署说明配置服务地址、运行环境和模型依赖。

## 真实链路边界

真实 Chat/Realtime 的效果、首响、端到端延迟、吞吐、并发和长时间稳定性必须在对应模型服务与昇腾环境中单独验收。离线 Demo 只证明客户端状态机、UI 和协议占位流程可运行。
