# Home Assistant 代理服务

这是一个用于Home Assistant的代理服务插件，支持Clash和Shadowrocket订阅地址，提供HTTP和SOCKS代理服务。

## 功能特点

- 支持Clash订阅地址直接导入
- 支持Shadowrocket订阅地址自动转换
- 提供HTTP代理服务（端口7890）
- 提供SOCKS代理服务（端口7891）
- 支持配置自动清理
- 支持手动启动/停止

## 安装说明

1. 在Home Assistant中添加自定义存储库：
   - 打开Home Assistant界面
   - 进入 **配置** > **加载项** > **加载项商店**
   - 点击右上角的三个点
   - 选择 **存储库**
   - 添加地址：`https://github.com/symi-daguo/ha-proxy-addon`
   - 点击 **添加**

2. 安装插件：
   - 刷新加载项商店页面
   - 在列表中找到 "代理服务"
   - 点击并选择 **安装**

## 配置说明

1. 基本配置：
   ```yaml
   subscription_type: "clash"  # 或 "shadowrocket"
   subscription_url: "你的订阅地址"
   clear_config: true
   ```

2. 配置项说明：
   - `subscription_type`: 订阅类型，可选 "clash" 或 "shadowrocket"
   - `subscription_url`: 你的订阅地址
   - `clear_config`: 是否在停止时自动清理配置

## 使用方法

1. 启动服务：
   - 完成配置后点击 **启动**
   - 等待服务启动完成（查看日志确认）

2. 使用代理：
   - HTTP代理：`http://HA的IP:7890`
   - SOCKS代理：`socks5://HA的IP:7891`

3. 关闭服务：
   - 完成使用后点击 **停止**
   - 如果启用了自动清理，配置会被自动删除

## 注意事项

- 本插件仅用于临时使用，建议使用后立即关闭
- 使用代理可能会影响网络性能
- 建议开启配置自动清理功能，以确保安全性
- 请勿分享你的订阅地址

## 支持系统

- Home Assistant OS
- Home Assistant Supervised

## 更新日志

### 1.0.0
- 初始版本发布
- 支持Clash和Shadowrocket订阅
- 提供HTTP和SOCKS代理服务 