---
name: mcp-youcom
description: Skills for web search via the You.com MCP Server (keyless free profile — no API key required). Used when users need online searching for current information, news, and facts.
---

# You.com Search
Executing Shell commands. The free-profile endpoint is keyless: no API key and no login required.

**MCP Server URL**: https://api.you.com/mcp?profile=free

## Web search
- `npx -y mcporter call --http-url "https://api.you.com/mcp?profile=free" you-search query="{keyword}" count=10`

Recency-limited search (news, prices, releases):
- `npx -y mcporter call --http-url "https://api.you.com/mcp?profile=free" you-search query="{keyword}" freshness=week count=10`

Site-scoped search:
- `npx -y mcporter call --http-url "https://api.you.com/mcp?profile=free" you-search query="{keyword} site:docs.python.org" count=5`

## Agent / tool discovery
- `npx -y mcporter call --http-url "https://api.you.com/mcp?profile=free" you-discover query="{task}" limit=10`

## Notes
- Snippets are not page content: read the returned URLs before answering.
- For full search plus page-content extraction (markdown or HTML), sign in with OAuth or set an API key from <https://you.com/platform/api-keys> on the authenticated profile <https://api.you.com/mcp>.