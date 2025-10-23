# Codex 配置指南

## Agents 配置

将 `AGENTS.md` 文件放置在 `~/.codex/` 目录下。

## MCP 配置

### 标准 MCP 配置示例

标准的 MCP 配置文件格式如下（JSON 格式）：

```json
{
  "mcpServers": {
    "mcp-router": {
      "command": "npx",
      "args": [
        "-y",
        "@mcp_router/cli@latest",
        "connect"
      ],
      "env": {
        "MCPR_TOKEN": "你的MCPR_TOKEN"
      }
    }
  }
}
```

### Codex 自动批转

``` sh
codex --dangerously-bypass-approvals-and-sandbox
```

### Windows 下 Codex 的 MCP 配置转换

Codex 使用 `config.toml` 文件进行配置。将上述标准配置转换为 Codex 配置如下：

```toml
[mcp_servers.mcp-router]
args = ["/c", "npx", "-y", "@mcp_router/cli@latest", "connect"]
command = "cmd"
type = "stdio"
startup_timeout_ms = 60_000

[mcp_servers.mcp-router.env]
MCPR_TOKEN = "你的MCPR_TOKEN"
SystemRoot = "C:\\Windows"
```

**⚠️ 转换要点：**

1. 配置格式从 JSON 转换为 TOML
2. `command` 从 `"npx"` 改为 `"cmd"`
3. `args` 参数开头需添加 `"/c"` 和 `"npx"`
4. **必须**添加环境变量 `SystemRoot = "C:\\Windows"`
