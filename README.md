# Hrizn Cursor plugin

Cursor Marketplace plugin for [Hrizn](https://www.hrizn.io) MCP.

Install in Cursor, sign in with OAuth, then use dealership inventory, content, and social tools. The MCP URL is `https://mcp.app.hrizn.io/mcp` — the same hosted server listed for Claude and other OAuth clients.

## Repo layout

This repo follows the [Cursor plugin template](https://github.com/cursor/plugin-template) multi-plugin layout with a single plugin:

- `.cursor-plugin/marketplace.json` — marketplace metadata
- `plugins/hrizn/` — plugin (`plugin.json`, `mcp.json`, skill, logo)

## Local validation

```bash
node scripts/validate-template.mjs
```

## Submission

When the listing is ready, send the repository URL to the Cursor team (Slack or `kniparko@anysphere.com`) per the [plugin template checklist](https://github.com/cursor/plugin-template).

Claude Connectors Directory is a separate listing of the same MCP URL. Do not change `mcp.json` to a Cursor-only host or API-key URL.
