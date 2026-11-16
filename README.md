# NiuGuo-Releases

「牛过周润发」安装包与更新清单的发布仓库。程序内部的「检查更新」只读这个仓库，源码仓库不对外。

## 下载

到 [Releases](../../releases) 页下载最新版：

| 通道 | 文件名 | 说明 |
|---|---|---|
| 正式版 | `NiuGuo-<版本>-setup.exe` | 稳定版，只推经过验证的版本 |
| 内测版 | `NiuGuo-Beta-<版本>-setup.exe` | 新功能先行，可能有问题 |

- 两个版本可以装在同一台机器上（不同安装目录、不同数据目录，互不影响）。
- 升级直接覆盖安装，配置、账本、日志都在 `%APPDATA%\NiuGuo`（内测版为 `%APPDATA%\NiuGuoBeta`），不会丢。
- 系统要求：Windows 10/11 64 位。安装需要管理员权限。
- 本仓库只保留**最新版本**，历史版本已归档、不再提供下载。已安装的旧版本请在程序里点右下角版本号升级。

## 更新清单

`latest.json`（正式版）与 `latest-beta.json`（内测版）是程序读取的更新清单，由发布脚本自动生成，请勿手改：

```json
{
  "channel": "stable",
  "version": "0.0.2",
  "url": "https://github.com/shiyi278314-eng/NiuGuo-Releases/releases/download/v0.0.2/NiuGuo-0.0.2-setup.exe",
  "mirrors": ["https://ghfast.top/<原地址>"],
  "sha256": "...",
  "min_version": "0.0.1",
  "notes": "更新说明",
  "force": false
}
```

- 程序只升不降，正式版只看 `latest.json`，内测版只看 `latest-beta.json`，两条线不互相干扰。
- 下载完成后会校验 `sha256`，不一致直接丢弃重下，不会安装坏包。
- 有持仓或挂单时只下载不安装，避免打断交易。

## 版本号

- 正式版：`0.0.1` 起递增。
- 内测版：`YY.MM.DD-beta.N`，N 为当天第几个构建。
