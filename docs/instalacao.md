# Instalação detalhada

webPosto é um servidor MCP remoto. Aponte seu cliente pra `https://api.mcp.ai/p_webposto`. Snippets rápidos: [INSTALL.md](../INSTALL.md).

| Cliente | URL | Auth |
|---|---|---|
| Claude Desktop | `https://api.mcp.ai/p_webposto` | OAuth 2.1 ou agent-auth |
| Cursor | `https://api.mcp.ai/p_webposto` | OAuth 2.1 ou agent-auth |
| VS Code (Copilot) | `https://api.mcp.ai/p_webposto` | OAuth 2.1 ou agent-auth |

A config JSON é a mesma em todos: só a URL, sem headers.

## Desinstalar

Remova o bloco `mcpServers.webposto` (ou `servers.webposto` no VS Code) do config do cliente e reinicie.
