# LegalSearch MCP Setup

LegalSearch is the official MCP Registry display name for Roop's public legal MCP.

- Display title: `LegalSearch`
- Canonical MCP Registry ID: `ai.roopslaw/legalsearch`
- Registry status: published and active

## Canonical Public URLs

- MCP endpoint: <https://mcp.roopslaw.ai/mcp>
- Health: <https://mcp.roopslaw.ai/health>
- Discovery JSON: <https://mcp.roopslaw.ai/.well-known/roop-public-mcp.json>
- Human/bot guide: <https://www.roopslawassist.com/bots>
- `llms.txt`: <https://www.roopslawassist.com/llms.txt>
- Official MCP Registry search: <https://registry.modelcontextprotocol.io/v0.1/servers?search=LegalSearch>

## Codex

Install:

```bash
codex mcp add roop_public_legal --url https://mcp.roopslaw.ai/mcp --bearer-token-env-var ROOP_PUBLIC_MCP_API_KEY
```

Verify:

```bash
codex mcp list
codex mcp get roop_public_legal
```

Equivalent `~/.codex/config.toml`:

```toml
[mcp_servers.roop_public_legal]
url = "https://mcp.roopslaw.ai/mcp"
bearer_token_env_var = "ROOP_PUBLIC_MCP_API_KEY"
```

Authenticated access:

```bash
export ROOP_PUBLIC_MCP_API_KEY="<set this locally from your Roop account>"
```

Do not commit shell profiles, config overlays, or CI secrets containing real tokens.

## Claude Code

Project-scoped install:

```bash
claude mcp add --transport http roop_public_legal https://mcp.roopslaw.ai/mcp
```

User-scoped install where supported:

```bash
claude mcp add --transport http --scope user roop_public_legal https://mcp.roopslaw.ai/mcp
```

Verify:

```bash
claude mcp list
```

Inside Claude Code, run:

```text
/mcp
```

For authenticated access, use the current Claude Code secure-header or environment-variable mechanism for your version. Do not store bearer tokens in a committed `.mcp.json`.

## Cursor

Add to `~/.cursor/mcp.json` or the project MCP file used by your workspace:

```json
{
  "mcpServers": {
    "roop_public_legal": {
      "url": "https://mcp.roopslaw.ai/mcp"
    }
  }
}
```

Restart or reload the agent environment if required.

## VS Code Agent Mode

Add `.vscode/mcp.json`:

```json
{
  "servers": {
    "roop_public_legal": {
      "type": "http",
      "url": "https://mcp.roopslaw.ai/mcp"
    }
  }
}
```

Enable the server in the tools picker if your VS Code agent client requires it.

## Generic JSON-RPC Checks

Initialize:

```bash
curl -fsS https://mcp.roopslaw.ai/mcp \
  -H 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","id":1,"method":"initialize","params":{}}'
```

List tools:

```bash
curl -fsS https://mcp.roopslaw.ai/mcp \
  -H 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","id":2,"method":"tools/list","params":{}}'
```

Call corpus status:

```bash
curl -fsS https://mcp.roopslaw.ai/mcp \
  -H 'content-type: application/json' \
  --data '{"jsonrpc":"2.0","id":3,"method":"tools/call","params":{"name":"roop.public.corpus.status","arguments":{}}}'
```

Authenticated call:

```bash
curl -fsS https://mcp.roopslaw.ai/mcp \
  -H 'content-type: application/json' \
  -H "authorization: Bearer ${ROOP_PUBLIC_MCP_API_KEY}" \
  --data '{"jsonrpc":"2.0","id":4,"method":"tools/list","params":{}}'
```

## Expected Tool Names

- `roop.public.judgments.search`
- `roop.public.judgments.get_packet`
- `roop.public.statutes.search`
- `roop.public.statutes.get_packet`
- `roop.public.corpus.status`

Always prefer tool discovery from the live MCP server over hardcoding this list.
