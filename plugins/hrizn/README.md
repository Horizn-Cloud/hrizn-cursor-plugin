# Hrizn

**Content Operating system for Automotive Dealerships.**

Connects Cursor to the hosted Hrizn MCP at `https://mcp.app.hrizn.io/mcp`.

Streamable HTTP + OAuth. This plugin does not ship a second MCP, API keys, or a Cursor-only Auth0 audience.

## After OAuth

The agent can use live rooftop tools your plan allows: inventory, dealer context, IdeaClouds and page creation, OEM-compliance checks, Social Hub, and Market Maker. Tool availability is per granted dealership — see `list_connected_sites`.

## Setup

1. In Hrizn Dealership Manager → **MCP**, choose dealerships and save.
2. Install the plugin and sign in when Cursor prompts.

```json
{
  "mcpServers": {
    "hrizn": {
      "url": "https://mcp.app.hrizn.io/mcp"
    }
  }
}
```
