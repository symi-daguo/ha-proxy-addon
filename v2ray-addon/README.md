# Home Assistant 代理服务

这个附加组件（Add-on）为 Home Assistant 提供代理服务，支持 Clash 和 Shadowrocket 订阅地址，可以临时开启用于远程升级 Home Assistant 系统和组件，完成后可以关闭。

## 功能

- 支持 Clash 订阅地址直接导入
- 支持 Shadowrocket 订阅地址自动转换
- 提供 HTTP 代理（7890端口）和 SOCKS 代理（7891端口）
- 简单易用的配置界面
- 支持手动开启和关闭，不会常驻运行
- 支持配置自动清理功能

## 使用方法

1. 在 Home Assistant 中安装此附加组件
2. 配置代理信息：
   - 选择订阅类型（Clash 或 Shadowrocket）
   - 输入订阅地址
   - 选择是否在关闭时清理配置（推荐开启）
3. 启动附加组件
4. 在需要使用代理的设备上设置代理：
   - HTTP 代理：
     - 地址：你的 Home Assistant 的 IP 地址
     - 端口：7890
   - SOCKS 代理：
     - 地址：你的 Home Assistant 的 IP 地址
     - 端口：7891
5. 完成更新或远程操作后，关闭附加组件以停止代理服务

## 注意事项

- 此插件仅供临时使用，完成升级后应当关闭
- 订阅地址应当是有效的 Clash 或 Shadowrocket 格式
- 使用代理时，网络性能可能会有所下降，这是正常的
- 建议启用配置自动清理功能，以确保安全性

## 技术支持

如需帮助，请参考：[new-pac GitHub Wiki](https://github.com/Alvin9999/new-pac/wiki) 