# OpenHarmony 适配说明

## 适配目标

当前路线面向 OpenHarmony NEXT PC：复用浮伴 Renderer 的产品交互，通过 ArkWeb 承载 Web UI，再由 ArkTS 能力桥接系统侧窗口、权限和生命周期能力。

## 工程组成

- `harmony/`：OpenHarmony NEXT PC 工程。
- `harmony/entry/src/main/ets/`：ArkTS 入口和系统能力桥接。
- `harmony/entry/src/main/resources/rawfile/renderer/`：同步后的 Renderer 资源。
- `harmony/scripts/sync-renderer.mjs`：从当前 Electron Renderer 同步界面资源。
- `materials/harmonyos/FloatPet-HarmonyPC-Demo-ArkWeb-signed.hap`：当前预览 HAP。

## 构建路径

项目记录的构建环境为 HarmonyOS 6.1.0 / API 23。源码仓库中的同步和构建入口如下：

```powershell
node .\harmony\scripts\sync-renderer.mjs
Set-Location .\harmony
D:\Tools\command-line-tools\bin\hvigorw.bat --mode module -p product=default assembleHap --no-daemon
```

## 当前边界

HAP 是适配路线的预览材料，实际安装和运行取决于设备型号、开发者签名、权限配置和本地 SDK。它用于说明 OpenHarmony 原生承载路径；Windows Electron Demo 仍是本次评审最直接的可运行入口。
