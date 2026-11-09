# Nexus 客户端发布

本仓库只用于构建与发布 Nexus 桌面客户端安装包，不包含源码。安装包在 [Releases](../../releases) 页面。

## 下载

| 系统 | 文件 |
|------|------|
| Windows 10 / 11（x64） | `Nexus_<版本>_x64-setup.exe` |
| Windows 11（ARM） | `Nexus_<版本>_arm64-setup.exe` |
| macOS 12 及以上（Intel / Apple 芯片） | `Nexus_<版本>_universal.dmg` |
| Linux（x64 / ARM64） | `Nexus_<版本>_amd64.AppImage` / `Nexus_<版本>_aarch64.AppImage`，或对应的 `.deb` |

`.sig`、`.app.tar.gz` 是自动更新使用的文件，不需要手动下载。可用 `SHA256SUMS` 校验下载的文件。

## 安装位置

- Windows：按当前用户安装到 `%LOCALAPPDATA%\CZL\Nexus`，不需要管理员权限；配置、数据与日志在同一目录的 `config`、`data`、`logs` 中
- macOS：把 Nexus 拖入“应用程序”；配置、数据与日志在 `~/Library/Application Support/CZL/Nexus`
- Linux：配置、数据与日志在 `~/.local/share/CZL/Nexus`

开启增强模式（TUN）时会请求一次管理员授权，把服务安装到只有管理员可写的系统目录（Windows `C:\Program Files\CZL\Nexus\service`，macOS `/Library/Application Support/CZL/Nexus/service`，Linux `/opt/CZL/Nexus/service`）。

卸载时会还原系统代理并移除增强模式服务；Windows 卸载界面中勾选“删除应用数据”才会删除配置与数据。
