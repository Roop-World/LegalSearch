# Basic Agent Prompts

## Setup Prompt

```text
Install Roop Public Legal MCP for this agent, using https://mcp.roopslaw.ai/mcp. Use the official public docs at https://www.roopslawassist.com/bots and https://www.roopslawassist.com/llms.txt. Do not use private endpoints. Start unauthenticated and tell me if the free limit requires ROOP_PUBLIC_MCP_API_KEY.
```

## Research Prompt

```text
Use Roop Public Legal MCP to research recent Indian case law on the right to privacy. Search public judgments first, fetch bounded packets where needed, and clearly separate MCP-grounded findings from your own analysis.
```

## Statute Prompt

```text
Use Roop Public Legal MCP to find public statute material relevant to the Indian Contract Act. Cite the MCP-returned public references and state any limits in the result.
```

## Auth Handoff Prompt

```text
The Roop MCP anonymous limit was reached. Stop unauthenticated probing. Tell me exactly which local environment variable or MCP config field needs my API key, but do not ask me to paste the key into chat.
```

