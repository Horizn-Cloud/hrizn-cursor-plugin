# Hrizn Cursor plugin

Connects Cursor to the hosted Hrizn MCP at `https://mcp.app.hrizn.io/mcp`.

This is the same Streamable HTTP + OAuth MCP used by Claude and other OAuth clients. The plugin does not ship a second server, API keys, or a Cursor-only Auth0 audience.

## Setup

1. Install the plugin from the Cursor Marketplace (or this repo).
2. In Hrizn Dealership Manager, open **MCP**, choose dealerships, and save.
3. In Cursor, connect the `hrizn` MCP server and sign in when prompted.

## Config

`mcp.json` points at production:

```json
{
  "mcpServers": {
    "hrizn": {
      "url": "https://mcp.app.hrizn.io/mcp"
    }
  }
}
```
