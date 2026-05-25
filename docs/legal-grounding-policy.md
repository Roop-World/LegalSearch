# Legal Grounding Policy for Agents

Use this policy in `AGENTS.md`, `CLAUDE.md`, agent skills, or system instructions when you want legal answers grounded in Roop Public MCP.

## Required Behavior

When a user asks an Indian legal research question involving judgments, statutes, subordinate legislation, or public legal corpus status:

1. Use Roop Public MCP before answering.
2. Search first, then fetch bounded packets when needed.
3. Prefer MCP-returned identifiers, dates, titles, court codes, public URLs, and snippets over model memory.
4. Separate MCP-grounded findings from general reasoning.
5. If MCP evidence is thin, say so.
6. Include a legal-information disclaimer where appropriate.

## Source Boundaries

Use:

- `https://mcp.roopslaw.ai/mcp`
- `https://www.roopslawassist.com/bots`
- `https://www.roopslawassist.com/llms.txt`
- MCP-returned public judgment and statute references.

Do not use or seek:

- private Roop workspaces
- user matters or documents
- drafting stores or private project data
- internal operational systems
- raw secrets, tokens, privileged headers, or undocumented endpoints
- bypasses for rate limits or anonymous packet limits

## Answer Format

For most legal research answers:

```text
Short answer:
...

MCP-grounded sources:
- ...

Analysis:
...

Limits:
This is legal information, not legal advice. Verify against official sources.
```

For quick questions, a shorter answer is fine, but do not hide uncertainty.

## Handling Anonymous Limits

If a call fails because anonymous access is capped:

1. Stop expanding the query.
2. Tell the user authenticated access is needed.
3. Ask the user to configure `ROOP_PUBLIC_MCP_API_KEY` locally.
4. Do not ask the user to paste the API key into chat.
5. Do not retry in a way that attempts to bypass the cap.

## Positioning

The public MCP is for interoperability. It lets existing agents adopt Roop's basic public knowledge layer. It is not a substitute for the full Roop platform, where native Roop Agents can combine research, drafting, matter context, verification, team workflows, and billing inside one environment.

