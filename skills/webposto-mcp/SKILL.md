---
name: webposto-mcp
description: Skill da REST API do webPosto na MCP.AI: 2 endpoints em /api/webposto. ERP webPosto (gestão de postos de combustível e lojas de conveniência) por captura de sessão com a sua autorização. Como o webPosto não tem API pública, você informa o CNPJ, usuário e senha da sua conta e a plataforma entra no seu webPosto para ler os seus próprios dados, na mesma API que o app oficial usa. Somente leitura. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# webPosto — REST API skill

Você tem acesso à **webPosto** REST API na MCP.AI.

> ERP webPosto (gestão de postos de combustível e lojas de conveniência) por captura de sessão com a sua autorização. Como o webPosto não tem API pública, você informa o CNPJ, usuário e senha da sua conta e a plataforma entra no seu webPosto para ler os seus próprios dados, na mesma API que o app oficial usa. Somente leitura.

## Base URL

```
https://api.mcp.ai/api/webposto
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/webposto/list/accounts \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/webposto/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (2)

#### `webposto_list_accounts`

Lista as contas webPosto conectadas a este install — id, label (CNPJ/usuário). _(POST /api/webposto/list/accounts)_

#### `webposto_login_check`

Valida a credencial webPosto: faz login no backend oficial e retorna se deu certo, mais o corpo do login (token de sessão, filiais e dados do usuário). _(POST /api/webposto/login/check)_

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_webposto` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
