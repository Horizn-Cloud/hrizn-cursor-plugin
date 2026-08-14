# Hrizn

**Content Operating system for Automotive Dealerships.**

Cursor Marketplace plugin for [Hrizn](https://www.hrizn.io). Connect Cursor to **your granted rooftops** over OAuth so the agent can work against live lot, content, and social data at `https://mcp.app.hrizn.io/mcp`.

## What Cursor can do after you connect

Available tools follow each rooftop’s Hrizn plan (not a Cursor-only subset):

- **Brief the store** — Dealer DNA, brand voice metadata, staff, CTAs, and target geography
- **Work the lot** — Search inventory, aging, merchandising health, and a single vehicle
- **Plan and publish content** — IdeaCloud research, citations, opportunities, articles, model landings, comparisons, and sales-event pages
- **Check ad copy** — OEM-oriented compliance guidance on pasted or Hrizn content (not legal advice)
- **Social Hub** — Presence, posts, media upload sessions, and review replies when Social Hub is on the plan
- **Market Maker** — Local listings, days supply, pricing vs market, appraisal, and stocking gaps on Unlimited

## Setup

1. In Hrizn, open **Dealership Manager → MCP**, choose Teams+ rooftops, and save.
2. Install this plugin in Cursor.
3. Connect the `hrizn` MCP server and sign in when Cursor prompts.

You do not paste API keys. If tools fail with a grant error, save rooftops on the MCP page and reconnect.

## Repo layout

Follows the [Cursor plugin template](https://github.com/cursor/plugin-template):

- `.cursor-plugin/marketplace.json` — listing metadata
- `plugins/hrizn/` — plugin, `mcp.json`, skill, logo

```bash
node scripts/validate-template.mjs
```

Do not point `mcp.json` at a Cursor-only host or an API-key URL.
