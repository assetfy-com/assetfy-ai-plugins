# Assetfy AI plugins

Plugins that connect AI assistants to the [Assetfy](https://assetfy.com) MCP server: official real estate data for Germany and Austria — Flurstück on the cadastral map, Bebauungsplan, Bodenrichtwert, GRZ/GFZ, buildings with Traufhöhe and Firsthöhe, terrain, 3D building models, aerial images and property listings.

The server runs at `https://mcp.assetfy.com/mcp` (Streamable HTTP, OAuth 2.1). All tools are read-only. An Assetfy account with a PROFESSIONAL or ENTERPRISE plan is required.

| Plugin | Client | Path |
|---|---|---|
| `assetfy` | Cursor | [`plugins/assetfy`](plugins/assetfy) |
| `assetfy` | Gemini CLI | [`gemini-extension.json`](gemini-extension.json) |

Also listed in the [official MCP Registry](https://registry.modelcontextprotocol.io) as `com.assetfy/mcp` and in the [Claude connector directory](https://claude.ai/directory/assetfy).

## Gemini CLI

```bash
gemini extensions install https://github.com/assetfy-com/assetfy-ai-plugins
```

Then sign in once with `/mcp auth assetfy`.

## Install by URL

Any MCP client that supports remote servers can connect directly:

```json
{
  "mcpServers": {
    "assetfy": { "url": "https://mcp.assetfy.com/mcp" }
  }
}
```

## Documentation and support

- Setup and examples: https://assetfy.com/produkt/ai-mcp-anbindung/
- Privacy: https://assetfy.com/datenschutz/
- Contact: hallo@assetfy.com

## Validate

```bash
node scripts/validate-template.mjs
```
