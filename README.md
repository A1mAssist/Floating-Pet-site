# 浮伴 Floating Pet

浮伴是一款面向桌面工作场景的全模态陪伴应用。它以透明置顶桌宠作为入口，在用户明确授权后，把语音、视觉和文字上下文带进一次可停止、可拒绝的协助流程。

本仓库用于提交开源鸿蒙系统技术创新作品相关材料，应用名称为“浮伴（Floating Pet）”，参考命题为“OpenHarmony Agent 鸿蒙原生智能多模态个人助理”。

## 评委入口

- [产品宣传页](https://a1massist.github.io/Floating-Pet-site/)
- [在线 Web Demo](https://floating-pet-web-demo.vercel.app/)
- [Windows 便携 Demo](https://github.com/A1mAssist/Floating-Pet-site/releases/download/windows-demo-0.1.0/Floating-Pet-Demo-Portable-0.1.0-x64.exe)
- [Windows Demo Release 说明](https://github.com/A1mAssist/Floating-Pet-site/releases/tag/windows-demo-0.1.0)
- [宣传片](./fuban-promo.mp4)
- [项目开发设计文档 PDF](./docs/development-design-document.pdf)
- [项目开发设计文档 DOCX](./docs/development-design-document.docx)

## 材料清单

| 材料 | 文件或入口 | 用途 |
| --- | --- | --- |
| 参赛作品简介 | [项目简介](./docs/project-introduction.md) | 说明问题、方案、模型分工和应用价值 |
| 项目文档 | [开发设计文档 PDF](./docs/development-design-document.pdf) / [DOCX](./docs/development-design-document.docx) | 按赛事提供的开发设计文档模板填写 |
| 项目视频 | [浮伴宣传片](./fuban-promo.mp4) | 展示 Windows Demo 的产品流程 |
| Windows Demo | [GitHub Release](https://github.com/A1mAssist/Floating-Pet-site/releases/tag/windows-demo-0.1.0) | 评委可下载并运行的便携版 |
| 技术可行性 | [技术可行性与部署说明](./docs/technical-feasibility.md) | 说明 Electron、模型服务、离线演示和复现条件 |
| OpenHarmony 材料 | [OpenHarmony 适配说明](./docs/harmonyos.md) | 说明 ArkWeb/ArkTS 延伸工程和 HAP 预览包 |
| 测试与边界 | [测试与验证报告](./docs/test-report.md) | 列出已验证能力、测试命令和 Fake 边界 |
| 操作说明 | [评审操作指南](./docs/demo-guide.md) | 帮助评委选择在线 Demo、Windows Demo 或宣传页 |
| 界面材料 | [产品界面截图](./materials/screenshots/product-ui.png) / [交互流程图](./materials/screenshots/interaction-flow.png) | 辅助理解产品结构 |
| 鸿蒙构建产物 | [ArkWeb HAP](./materials/harmonyos/FloatPet-HarmonyPC-Demo-ArkWeb-signed.hap) | OpenHarmony NEXT PC 预览材料 |

## 产品主张

浮伴从“感知关闭”开始。用户可以分别打开麦克风、摄像头和指定屏幕；重复线索经过确认后才出现主动询问；用户拒绝、暂停采集、开启勿扰或结束陪伴时，输入链路可以立即收回。

模型服务可用时，Python 适配服务把 Chat 和 Realtime 请求转换为 MiniCPM-o 可处理的输入，并把文字、视觉帧、音频和增量结果送回桌面协助卡。模型服务不可用时，Windows Demo 和 Web Demo 使用带有 Fake/离线标识的确定性流程展示客户端交互，不把固定回复写成任意屏幕理解。

## 版本边界

- Windows Demo 是评审用便携构建，默认静音；Windows 可能对未签名构建显示安全提示。
- 在线 Web Demo 使用浏览器本地 Fake Adapter 和本地存储，不请求麦克风、摄像头或屏幕权限，不连接模型服务。
- OpenHarmony HAP 是当前 ArkWeb/ArkTS 适配路线的预览材料，实际安装还取决于目标设备、签名和开发环境。
- 私有源码仓库、模型权重、服务凭据、私钥、签名证书和构建缓存不放入本提交仓库。

## 源码与联系入口

完整源码与工程文档在 [Floating-Pet 源码仓库](https://github.com/A1mAssist/Floating-Pet)。本仓库只保留评审所需的公开材料和下载入口。
