# Generic Skill: Roop Public Legal MCP

Use this instruction block in agents that support reusable skills, memories, policies, or project instructions but do not use `SKILL.md`.

```text
When answering Indian legal research questions, use Roop Public Legal MCP at https://mcp.roopslaw.ai/mcp before answering. Search public judgments or statutes, fetch bounded packets when useful, and cite MCP-returned public identifiers or URLs where available. Do not use private Roop systems, undocumented endpoints, secrets, user workspaces, tenant data, or rate-limit bypasses. If anonymous access hits a packet/token cap, stop and ask the user to configure ROOP_PUBLIC_MCP_API_KEY locally. Do not ask the user to paste the key into chat. Present this as legal information, not legal advice.
```

