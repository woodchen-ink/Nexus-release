# Nexus 客户端发布

本仓库只用于构建与发布 Nexus 桌面客户端安装包，不包含源码。安装包在 [Releases](../../releases) 页面，也通过 CZL Connect 的固定地址分发（客户端自动更新读取 `https://connect.czl.net/dl/nexus/latest.json`）。

## 下载

| 系统 | 文件 | CZL Connect 别名 |
|------|------|------|
| Windows 10 / 11（x64） | `Nexus_<版本>_x64-setup.exe` | `windows-x64` |
| Windows 11（ARM） | `Nexus_<版本>_arm64-setup.exe` | `windows-arm64` |
| macOS 12 及以上（Intel / Apple 芯片） | `Nexus_<版本>_universal.dmg` | `macos-universal` |
| Linux x64（Ubuntu / Debian 等） | `Nexus_<版本>_amd64.deb` | `linux-x64-deb` |
| Linux ARM64（Ubuntu / Debian 等） | `Nexus_<版本>_arm64.deb` | `linux-arm64-deb` |

`Nexus_<版本>_universal.app.tar.gz`（别名 `macos-update`，不在下载页显示）是 macOS 自动更新使用的文件，不需要手动下载。可用 `SHA256SUMS` 校验下载的文件；客户端自动更新时按 CZL Connect 清单中的大小与 SHA-256 校验，不符时不会安装。

## 安装位置

- Windows：按当前用户安装到 `%LOCALAPPDATA%\CZL\Nexus`，不需要管理员权限；配置、数据与日志在同一目录的 `config`、`data`、`logs` 中
- macOS：把 Nexus 拖入“应用程序”；配置、数据与日志在 `~/Library/Application Support/CZL/Nexus`
- Linux：配置、数据与日志在 `~/.local/share/CZL/Nexus`

开启增强模式（TUN）时会请求一次管理员授权，把服务安装到只有管理员可写的系统目录（Windows `C:\Program Files\CZL\Nexus\service`，macOS `/Library/Application Support/CZL/Nexus/service`，Linux `/opt/CZL/Nexus/service`）。

卸载时会还原系统代理并移除增强模式服务；Windows 卸载界面中勾选“删除应用数据”才会删除配置与数据。
