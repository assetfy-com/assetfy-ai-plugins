# Assetfy AI plugins

Plugins that connect AI assistants to the [Assetfy](https://assetfy.com) MCP server: official real estate data for Germany and Austria — Flurstück on the cadastral map, Bebauungsplan, Bodenrichtwert, GRZ/GFZ, buildings with Traufhöhe and Firsthöhe, terrain, 3D building models, aerial images and property listings.

The server runs at `https://mcp.assetfy.com/mcp` (Streamable HTTP, OAuth 2.1). All tools are read-only. An Assetfy account with a PROFESSIONAL or ENTERPRISE plan is required.

| Plugin | Client | Path |
|---|---|---|
| `assetfy` | Claude (Claude Code, Cowork, chat) and Cursor | [`plugins/assetfy`](plugins/assetfy) |
| `assetfy` | ChatGPT and Codex | [`plugins/chatgpt`](plugins/chatgpt) (ZIP under [Releases](https://github.com/assetfy-com/assetfy-ai-plugins/releases)) |
| `assetfy` | Gemini CLI | [`gemini-extension.json`](gemini-extension.json) |
| `assetfy` | Antigravity | [`plugin.json`](plugin.json), [`mcp_config.json`](mcp_config.json) |

## Where Assetfy is listed

- [Anthropic Claude directory](https://claude.ai/directory/connectors/assetfy): Assetfy connector for Claude on the web, desktop and mobile, Claude Code and Cowork
- [Official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers/com.assetfy%2Fmcp/versions/latest): `com.assetfy/mcp`

## Claude

In Claude (web, desktop, mobile): open the [Assetfy connector in the Claude directory](https://claude.ai/directory/connectors/assetfy) and select **Connect**, then sign in with your Assetfy account.

In Claude Code:

```bash
claude mcp add --transport http assetfy https://mcp.assetfy.com/mcp
```

Then run `/mcp` in Claude Code and sign in with your Assetfy account.

## Gemini CLI

```bash
gemini extensions install https://github.com/assetfy-com/assetfy-ai-plugins
```

Then sign in once with `/mcp auth assetfy`.

## Antigravity

```bash
agy plugin install https://github.com/assetfy-com/assetfy-ai-plugins
```

Then authenticate under Agent settings → Customizations.

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
