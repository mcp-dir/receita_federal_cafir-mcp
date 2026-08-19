---
name: receita_federal_cafir-mcp
description: Skill da REST API do Receita Federal: Cafir na MCP.AI: 1 endpoint em /api/receita_federal_cafir. Receita Federal: Cafir, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Receita Federal: Cafir — REST API skill

Você tem acesso à **Receita Federal: Cafir** REST API na MCP.AI.

> Receita Federal: Cafir, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/receita_federal_cafir
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
curl -X POST https://api.mcp.ai/api/receita_federal_cafir/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cib":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/receita_federal_cafir/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `receita_federal_cafir_consultar`

Receita Federal: Cafir, consulta em fonte oficial. _(POST /api/receita_federal_cafir/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cib` | string | Sim | Parâmetro de consulta "cib". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_receita_federal_cafir` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
