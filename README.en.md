# webPosto

### webPosto for Claude, ChatGPT and AI agents

webPosto ERP (management for gas stations and convenience stores) via session capture with your authorization. Since webPosto has no public API, you provide your account CNPJ, user and password and the platform logs into your webPosto to read your own data, on the same API the official app uses. Read-only.

- 📊 **2 tools**
- ✏️ **Read and write**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `webPosto`, URL `https://api.mcp.ai/p_webposto`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=webposto&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF93ZWJwb3N0byJ9)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=webposto&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_webposto%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_webposto
```

---

## 2 tools

| Tool | Description |
|---|---|
| `webposto_list_accounts` | Lista as contas webPosto conectadas a este install — id, label (CNPJ/usuário). |
| `webposto_login_check` | Valida a credencial webPosto: faz login no backend oficial e retorna se deu certo, mais o corpo do login (token de sessão, filiais e dados do usuário). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_webposto` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
