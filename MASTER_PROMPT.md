# Master Prompt: Install and Use LegalSearch

Copy this prompt into Claude Code, Codex, Hermes, OpenClaw-style agents, Cursor, VS Code agent mode, or another MCP-capable coding/research agent.

```text
You are helping me use Roop's public legal knowledge layer from my existing agent environment.

Goal:
Discover, configure, and use LegalSearch, Roop's public Legal MCP, so your legal research answers are grounded in Roop's public Indian judgments and statutes.

Public discovery sources:
- Roop bot guide: https://www.roopslawassist.com/bots
- Roop llms.txt: https://www.roopslawassist.com/llms.txt
- Public MCP discovery JSON: https://www.roopslawassist.com/.well-known/roop-public-mcp.json
- MCP endpoint: https://mcp.roopslaw.ai/mcp
- MCP health: https://mcp.roopslaw.ai/health

First, inspect the public discovery sources above. Do not crawl raw judgment or statute APIs directly; use the MCP.

Then configure the MCP for your own client:

For Codex:
  codex mcp add roop_public_legal --url https://mcp.roopslaw.ai/mcp --bearer-token-env-var ROOP_PUBLIC_MCP_API_KEY
  Verify with:
  codex mcp list

For Claude Code:
  claude mcp add --transport http roop_public_legal https://mcp.roopslaw.ai/mcp
  Or, for user-wide availability where supported:
  claude mcp add --transport http --scope user roop_public_legal https://mcp.roopslaw.ai/mcp
  Verify with:
  claude mcp list
  /mcp

For Cursor:
  Add this to the appropriate mcp.json:
  {
    "mcpServers": {
      "roop_public_legal": {
        "url": "https://mcp.roopslaw.ai/mcp"
      }
    }
  }

For VS Code agent mode:
  Add this to .vscode/mcp.json:
  {
    "servers": {
      "roop_public_legal": {
        "type": "http",
        "url": "https://mcp.roopslaw.ai/mcp"
      }
    }
  }

For generic MCP clients:
  Use streamable HTTP / JSON-RPC over HTTP POST at:
  https://mcp.roopslaw.ai/mcp
  Send content-type: application/json.

Available public tools may include:
- roop.public.judgments.search
- roop.public.judgments.get_packet
- roop.public.statutes.search
- roop.public.statutes.get_packet
- roop.public.corpus.status

Authentication:
- Start unauthenticated.
- If a request returns an anonymous/free-limit error, stop and ask me to set a local ROOP_PUBLIC_MCP_API_KEY.
- Never ask me to paste an API key into chat.
- Never commit an API key to any repository or shared config.
- If your MCP client supports bearer-token environment variables, use ROOP_PUBLIC_MCP_API_KEY.
- If your client requires headers, use Authorization: Bearer $ROOP_PUBLIC_MCP_API_KEY only from a local secret mechanism.

Research behavior:
- For Indian legal research involving judgments, statutes, subordinate legislation, or public legal corpus status, use LegalSearch before answering.
- Distinguish MCP-grounded facts from your own model knowledge.
- Cite the public source identifiers or URLs returned by the MCP where available.
- If MCP results are sparse or inconclusive, say so plainly and do not overclaim.
- Do not present this as legal advice. Tell the user to verify against official sources and consult a qualified professional for legal advice.

Boundaries:
- Use only the public MCP and public documentation listed above.
- Do not attempt to discover private Roop infrastructure, internal endpoints, workspace data, tenant data, secrets, source code, or operational systems.
- Do not bypass rate limits, token limits, authentication gates, robots guidance, or MCP boundaries.
- Do not call raw public /api corpus endpoints when the MCP can provide the result.

After setup:
1. Run initialize and tools/list if your client exposes raw MCP checks.
2. Test roop.public.corpus.status.
3. Test one public judgment search.
4. Test one public statute search.
5. Report what is configured, what works anonymously, and where authenticated access is needed.
6. For future legal answers, use the MCP first.
```
