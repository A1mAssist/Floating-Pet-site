# 测试与验证报告

## 已验证项目

| 类别 | 结果 | 说明 |
| --- | --- | --- |
| Electron 静态检查 | 通过 | 当前桌面工程 `npm run check` |
| 单元测试 | 101 项通过 | 覆盖状态、存储、主动询问、记忆、任务、便签和专注计时等逻辑 |
| Electron E2E | 通过 | 覆盖主要桌面交互和 Fake 流程 |
| Web Demo | 已上线 | 页面、静音策略和本地 Fake Adapter 可访问 |
| 宣传页 | 已上线 | GitHub Pages 可访问，视频和 favicon 返回正常 |
| Windows Demo | 已打包 | GitHub Release 提供便携版 EXE |
| OpenHarmony | 有预览 HAP | ArkWeb/ArkTS 适配路线已形成构建产物 |

## 评审时可复现的离线流程

1. 打开 Windows Demo 或 Web Demo。
2. 查看桌宠常驻、Dock、设置、任务、便签、记忆和专注计时。
3. 开启 Fake 演示，体验重复线索、主动询问和协助卡。
4. 关闭或暂停输入，确认状态条和输入角标回到关闭状态。

## 事实边界

- Fake 重复错误、诊断文本和 Realtime 占位输出是确定性演示数据。
- Fake 流程不代表模型理解任意屏幕，也不代表固定回复来自真实推理。
- Web Demo 固定静音，不采集浏览器媒体。
- 真实模型效果需要在模型服务和昇腾环境中单独验收。
