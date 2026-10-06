# RankRoot MCP: AI visibility audit for any website

**Remote MCP server** that tells you how visible a website is to AI answer engines (ChatGPT, Perplexity, Claude, Google AI Overviews) and AI agents, then generates the fixes.

- Endpoint (Streamable HTTP, no auth required): `https://rankroot-ai.netlify.app/api/mcp`
- Official MCP Registry: `io.github.zachhhhh/rankroot`
- Website: https://rankroot-ai.netlify.app · Docs: https://rankroot-ai.netlify.app/agents

## Tools

| Tool | What it does |
|---|---|
| `audit_ai_visibility(url)` | 0-100 score across AI crawler access (GPTBot, OAI-SearchBot, PerplexityBot, ClaudeBot…), answer-engine content, structured data and agent readiness (llms.txt, MCP/OpenAPI, pricing, docs). Returns prioritized fixes, a shareable report link and a badge. |
| `generate_ai_visibility_files(url)` | Generates a ready-to-publish `llms.txt`, an AI-bot-friendly `robots.txt` and schema.org JSON-LD from the site's homepage. |

## Install

Claude Desktop / Cursor / any MCP client:

```json
{
  "mcpServers": {
    "rankroot": { "url": "https://rankroot-ai.netlify.app/api/mcp" }
  }
}
```

Claude Code:

```bash
claude mcp add --transport http rankroot https://rankroot-ai.netlify.app/api/mcp
```

Then ask: *"Audit example.com's AI visibility and give me the llms.txt."*

## Limits & Pro

Free: 20 audits per 10 minutes per IP. [RankRoot Pro](https://rankroot-ai.netlify.app/#pricing) adds full-site audits (up to 200 pages), whole-site llms.txt / llms-full.txt / JSON-LD generation and a key for higher API/MCP limits: send `Authorization: Bearer <key>`.

## HTTP API

```
GET https://rankroot-ai.netlify.app/api/audit?url=example.com
```

OpenAPI: https://rankroot-ai.netlify.app/openapi.json

License: MIT (this README and config). The hosted service is operated by RankRoot.
