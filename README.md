# webPosto

### webPosto para Claude, ChatGPT e agentes de IA

ERP webPosto (gestão de postos de combustível e lojas de conveniência) por captura de sessão com a sua autorização. Como o webPosto não tem API pública, você informa o CNPJ, usuário e senha da sua conta e a plataforma entra no seu webPosto para ler os seus próprios dados, na mesma API que o app oficial usa. Somente leitura.

- 📊 **2 ferramentas**
- ✏️ **Leitura e escrita**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `webPosto` e **URL** `https://api.mcp.ai/p_webposto`.

### Cursor

[➕ Instalar webPosto no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=webposto&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF93ZWJwb3N0byJ9)

### VS Code (Copilot Chat)

[➕ Instalar webPosto no VS Code](vscode:mcp/install?name=webposto&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_webposto%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_webposto
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Minha conexão do webPosto está funcionando?
```

---

## 2 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `webposto_list_accounts` | Lista as contas webPosto conectadas a este install — id, label (CNPJ/usuário). |
| `webposto_login_check` | Valida a credencial webPosto: faz login no backend oficial e retorna se deu certo, mais o corpo do login (token de sessão, filiais e dados do usuário). |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Planos a partir do tier grátis. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Sub-processadores**: Quality Automação (webPosto), o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_webposto`.


---

## Suporte

- 📧 [webposto@mcp.ai](mailto:webposto@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/webposto-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_webposto` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
