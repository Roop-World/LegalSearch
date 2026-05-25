---
name: roop-public-legal-mcp
description: Use Roop Public Legal MCP to ground Indian legal research in public judgments and statutes. Use when a user asks about Indian law, public judgments, public statutes, MCP setup for Roop, legal corpus grounding, citation-backed legal research, or authenticated handoff with ROOP_PUBLIC_MCP_API_KEY.
---

# Roop Public Legal MCP

## Overview

Use the public MCP at `https://mcp.roopslaw.ai/mcp` before answering Indian legal research questions that need public judgment or statute grounding.

## Setup Check

If the MCP is not configured, install it:

```bash
codex mcp add roop_public_legal --url https://mcp.roopslaw.ai/mcp --bearer-token-env-var ROOP_PUBLIC_MCP_API_KEY
```

Verify:

```bash
codex mcp list
```

Do not ask the user to paste an API key into chat. If authenticated access is needed, ask them to set `ROOP_PUBLIC_MCP_API_KEY` locally.

## Grounding Workflow

1. Use MCP discovery and tool listing if the available tool names are unknown.
2. Search public judgments or statutes using Roop MCP.
3. Fetch bounded packets only when needed.
4. Cite MCP-returned public identifiers, dates, titles, court codes, URLs, or snippets when available.
5. Distinguish MCP-grounded facts from model reasoning.
6. If evidence is sparse, say so plainly.
7. Include a legal-information disclaimer where appropriate.

## Boundaries

Use only public Roop MCP and public Roop documentation. Do not seek private workspaces, matters, user data, internal systems, privileged tools, secrets, undocumented endpoints, or rate-limit bypasses.

If an anonymous request hits a packet or token cap, stop and ask the user to configure authenticated access through `ROOP_PUBLIC_MCP_API_KEY`.

## Public References

- MCP endpoint: `https://mcp.roopslaw.ai/mcp`
- Bot guide: `https://www.roopslawassist.com/bots`
- Discovery: `https://www.roopslawassist.com/.well-known/roop-public-mcp.json`
- `llms.txt`: `https://www.roopslawassist.com/llms.txt`
