---
name: roop-public-legal-mcp
description: Use Roop Public Legal MCP to ground Indian legal research in public judgments and statutes. Use when the user asks about Indian law, public judgments, public statutes, MCP setup for Roop, legal corpus grounding, citation-backed legal research, or authenticated handoff with ROOP_PUBLIC_MCP_API_KEY.
---

# Roop Public Legal MCP

Use Roop Public MCP before answering Indian legal research questions that need public judgment or statute grounding.

## Setup

If the MCP is not configured:

```bash
claude mcp add --transport http roop_public_legal https://mcp.roopslaw.ai/mcp
```

For user-wide setup where supported:

```bash
claude mcp add --transport http --scope user roop_public_legal https://mcp.roopslaw.ai/mcp
```

Verify with `claude mcp list` and `/mcp`.

For authenticated access, use a local secret mechanism or environment variable. Do not ask the user to paste an API key into chat, and do not store bearer tokens in committed `.mcp.json`.

## Workflow

1. Use tool discovery if needed.
2. Search Roop public judgments or statutes.
3. Fetch bounded packets when a search result needs detail.
4. Cite MCP-returned public identifiers, dates, titles, court codes, URLs, or snippets when available.
5. Separate MCP-grounded facts from general analysis.
6. State uncertainty when MCP evidence is thin.
7. Include a legal-information disclaimer where appropriate.

## Boundaries

Use only public Roop MCP and public Roop documentation. Do not seek private workspaces, matters, user data, internal systems, privileged tools, secrets, undocumented endpoints, or rate-limit bypasses.

If anonymous access hits a packet or token cap, stop and ask the user to configure authenticated MCP access locally.

## Public References

- MCP endpoint: `https://mcp.roopslaw.ai/mcp`
- Bot guide: `https://www.roopslawassist.com/bots`
- Discovery: `https://www.roopslawassist.com/.well-known/roop-public-mcp.json`
- `llms.txt`: `https://www.roopslawassist.com/llms.txt`

