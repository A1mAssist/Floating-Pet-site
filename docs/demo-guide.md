# 评审操作指南

## 推荐顺序

1. 先打开[产品宣传页](https://a1massist.github.io/Floating-Pet-site/)，了解产品定位并播放宣传片。
2. 再运行 [Windows 便携 Demo](https://github.com/A1mAssist/Floating-Pet-site/releases/download/windows-demo-0.1.0/Floating-Pet-Demo-Portable-0.1.0-x64.exe)，体验桌面形态。
3. 没有 Windows 环境时，打开[在线 Web Demo](https://floating-pet-web-demo.vercel.app/)。
4. 需要查看设计细节时，阅读[开发设计文档 PDF](./development-design-document.pdf)和[技术可行性说明](./technical-feasibility.md)。

## Windows Demo 信息

- 文件：`Floating-Pet-Demo-Portable-0.1.0-x64.exe`
- 平台：Windows 10/11 x64
- 体积：约 86 MB
- SHA-256：`C7DAA001D8A804E0CA35FA827C6FBC47F06231198EC5859F4608D35E67FB32B6`
- 说明：演示构建未配置商业代码签名，Windows 可能显示安全提示；Demo 默认静音。

## 评审关注点

- 桌宠常驻、拖拽、边缘吸附、托盘和键盘操作。
- 麦克风、摄像头和屏幕输入的独立授权与暂停。
- 重复线索确认后的主动询问，以及用户拒绝路径。
- 记忆、任务、便签和专注计时的本地功能。
- Fake/离线状态的明确标识，以及模型服务不可用时的产品边界。
