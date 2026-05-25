<p align="center">
  <img src="assets/roop-chevron-mark.svg" alt="Roop chevron mark" width="96" />
</p>

# LegalSearch Agent Kit

LegalSearch is Roop's public MCP for grounding external agents in Roop's public Indian judgments and statutes without adopting the full Roop platform or migrating an existing agent stack.

This repository gives agent users a copy-paste master prompt, MCP setup snippets, and starter skills for Gemini agents, Codex, Claude Code, Hermes, OpenClaw-style agents, Cursor, VS Code agent mode, and other MCP-capable tools.

Registry name:

- Display title: `LegalSearch`
- Canonical MCP Registry ID: `ai.roopslaw/legalsearch`
- Official MCP Registry status: published and active

## Public Endpoints

- MCP endpoint: <https://mcp.roopslaw.ai/mcp>
- Health: <https://mcp.roopslaw.ai/health>
- Discovery JSON: <https://mcp.roopslaw.ai/.well-known/roop-public-mcp.json>
- Roop bot guide: <https://www.roopslawassist.com/bots>
- Roop llms.txt: <https://www.roopslawassist.com/llms.txt>
- Official MCP Registry search: <https://registry.modelcontextprotocol.io/v0.1/servers?search=LegalSearch>

## What LegalSearch Provides

- Public judgment search and bounded judgment packets.
- Public statute and subordinate-legislation search and bounded packets.
- Public corpus status.
- A vendor-neutral grounding workflow for agents that already support MCP.

## What It Does Not Provide

- Private workspaces, matters, documents, drafts, or user data.
- Internal Roop systems, operational endpoints, non-public technical details, secrets, or privileged tools.
- Legal advice. Agents must tell users to verify legal work against official sources and consult a qualified professional where appropriate.

## Quick Start

Give your agent the master prompt in [MASTER_PROMPT.md](MASTER_PROMPT.md).

For direct setup instructions, see [docs/mcp-setup.md](docs/mcp-setup.md).

For answer behavior and legal grounding rules, see [docs/legal-grounding-policy.md](docs/legal-grounding-policy.md).

## Why Use Roop's Platform Too?

LegalSearch is a knowledge layer for interoperability. It is intentionally bounded. For sustained legal work, Roop's native platform and indigenous Roop Agents can be cheaper, faster, and more powerful because research, drafting, matter context, verification, collaboration, and billing are integrated rather than stitched together by an external agent.

See [docs/platform-and-pricing-positioning.md](docs/platform-and-pricing-positioning.md) for responsible positioning.

## Security

Do not commit API keys. Use local environment variables such as `ROOP_PUBLIC_MCP_API_KEY` for authenticated MCP access. See [SECURITY.md](SECURITY.md).

## License

MIT. See [LICENSE](LICENSE).
