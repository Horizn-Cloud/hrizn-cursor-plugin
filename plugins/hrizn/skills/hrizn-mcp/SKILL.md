---
name: hrizn-mcp
description: Use Hrizn MCP tools for dealership inventory, content, IdeaClouds, and social. Apply when the user asks about vehicles, listings, articles, reviews, or Social Hub work in Hrizn.
---

# Hrizn MCP

## When to use

- Inventory search, stats, or vehicle details for a connected rooftop
- Content, IdeaClouds, or compliance workflows
- Social Hub posts, reviews, or presence

## Auth and rooftops

1. The user must complete OAuth when Cursor prompts (Hrizn login).
2. Dealerships are granted in Hrizn Dealership Manager → **MCP**, not in this plugin.
3. If tools fail with a grant or 403 error, tell the user to save at least one Teams+ rooftop on the MCP page, then reconnect.
4. When multiple rooftops are granted, call `list_connected_sites` and pass `site_id` on later tools.

## Instructions

1. Prefer Hrizn MCP tools over guessing inventory or CMS data.
2. Do not invent VINs, prices, or published URLs.
3. Do not ask for `hzk_` API keys. This plugin uses OAuth only.
4. Follow tool descriptions for confirmation flags on mutating tools (`dry_run`, `user_confirmed`, `preview_token`).
