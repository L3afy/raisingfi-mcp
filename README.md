# Raising.fi MCP Server

Startup funding data inside your AI assistant. Ask Claude, ChatGPT, Grok, or Cursor who just raised, who led the round, and who to contact.

Raising.fi is a real-time startup funding-intelligence platform. This is a hosted (remote) MCP server: there is nothing to install or run locally.

- **Connector URL:** `https://raising.fi/api/mcp`
- **Transport:** Streamable HTTP
- **Auth:** OAuth sign-in (no API key to paste)
- **Website:** https://raising.fi/mcp
- **Docs:** https://raising.fi/developers#mcp

## Tools

| Tool | What it does |
|---|---|
| `search_raises` | Search recent funding rounds by industry, round type, location, or free text, newest first. Returns amount, lead investors, website, and HQ. |
| `get_founder` | Top decision-maker for a company website: title, email, email confidence rating, and LinkedIn. |
| `get_account` | Your plan, tokens used, and tokens left. |

## Setup

**Claude Code**
```
claude mcp add --transport http raising https://raising.fi/api/mcp
```

**Codex**
```
codex mcp add raising --url https://raising.fi/api/mcp
```

**Gemini CLI**
```
gemini mcp add --transport http -s user raising https://raising.fi/api/mcp
```

**Cursor, VS Code, and other MCP clients** (`mcp.json`)
```json
{
  "mcpServers": {
    "raising": {
      "url": "https://raising.fi/api/mcp"
    }
  }
}
```

**Claude, ChatGPT, Grok:** add a custom connector with the URL `https://raising.fi/api/mcp`, then sign in to Raising.fi when prompted.

## Example prompts

- Which fintech startups raised money this week, and who led each round?
- I want to pitch Payhawk, Count, and NABU. Who's the best person to contact at each, with email and LinkedIn?
- I sell CRM software. Which SaaS companies raised the most money since May, and which look like the best fit?
- Which startups have been raising rounds back to back this year?

## Pricing

MCP access is included on Raising.fi Growth and Enterprise plans. One token per raise returned, one per contact lookup. See https://raising.fi/developers#mcp.

## Support

hello@raising.fi
