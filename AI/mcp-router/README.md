# MCP Servers 配置文件

本配置文件由 mcp-router [<sup>1</sup>](https://github.com/mcp-router/mcp-router) 导出。

## 配置说明

### Exa API 配置

Exa 提供免费使用额度。请按照以下步骤获取并配置您的 API Key：

1. 访问 Exa API Dashboard [<sup>2</sup>](https://dashboard.exa.ai/api-keys) 申请您的 API Key
2. 将配置文件中的 `EXA_API_KEY` 替换为您申请到的实际 Key

## 常见问题

### MCP 启动失败

如果遇到 MCP 启动失败的问题，请先在终端中执行对应的mcp命令，例如：

```bash
npx -y @wonderwhy-er/desktop-commander@latest
```
