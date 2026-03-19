# OpenClaw 配置说明

## Feishu 配置

在布丁电脑上需要配置以下环境变量或运行命令：

```bash
# 飞书应用配置
openclaw config set channels.feishu.enabled true
openclaw config set channels.feishu.accounts.default.appId "cli_a925003740ba1ccb"
openclaw config set channels.feishu.accounts.default.appSecret "cli_xxxxxxxxxxxxx"  # 从飞书后台复制
```

## 获取 App Secret

1. 打开 https://open.feishu.cn/app/
2. 找到应用 "cli_a925003740ba1ccb"
3. 进入「凭证与基础信息」
4. 复制 App Secret

## 其他需要同步的配置

```bash
# 启用飞书频道
openclaw config set channels.feishu.enabled true
openclaw config set channels.feishu.connectionMode "websocket"
openclaw config set channels.feishu.dmPolicy "open"

# 重启服务
openclaw gateway restart
```
