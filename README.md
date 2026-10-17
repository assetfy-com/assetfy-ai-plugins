<p align="center">
  <img src="plugins/assetfy/assets/logo.png" alt="Assetfy" width="96">
</p>

<h1 align="center">Assetfy MCP Server</h1>

<p align="center">
  <b>Official real estate data for Germany and Austria in your AI assistant: Flurstück, Bebauungsplan, Bodenrichtwert, GRZ/GFZ, buildings with Traufhöhe and Firsthöhe, terrain, 3D building models, aerial images and property listings.</b>
</p>

<p align="center">
  <a href="https://registry.modelcontextprotocol.io/v0.1/servers/com.assetfy%2Fmcp/versions/latest"><img src="https://img.shields.io/badge/MCP_Registry-com.assetfy%2Fmcp-000000?logo=modelcontextprotocol&logoColor=white" alt="MCP Registry: com.assetfy/mcp"></a>
  <img src="https://img.shields.io/badge/Auth-OAuth_2.1-09A76C" alt="Auth: OAuth 2.1">
  <img src="https://img.shields.io/badge/Tools-39_read--only-09A76C" alt="39 read-only tools">
  <img src="https://img.shields.io/badge/Coverage-Germany_%7C_Austria-112240" alt="Coverage: Germany and Austria">
  <a href="LICENSE"><img src="https://img.shields.io/github/license/assetfy-com/assetfy-ai-plugins?color=112240" alt="License: MIT"></a>
</p>

<p align="center">
  <a href="https://assetfy.com/produkt/ai-mcp-anbindung/"><b>Setup &amp; examples</b></a> ·
  <a href="https://www.youtube.com/watch?v=_VAQGN_CzsQ"><b>Demo video</b></a> ·
  <a href="https://assetfy.com/pricing/"><b>Plans</b></a> ·
  <a href="#data-and-security"><b>Data &amp; security</b></a>
</p>

---

Ask in plain language about an address, a Flurstück (Gemarkung, Flur, Flurstücksnummer) or a property listing. The answer comes from the official cadastre, the 3D building models (LoD2), Bodenrichtwerte and Bebauungspläne of the German states, and from the Austrian cadastre (BEV). Every parcel and listing in a result links to the Assetfy map, where its outline, Bebauungsplan, buildings and aerial image are shown together.

Built for brokers, project developers, homebuilders, architects, valuers and investors who check sites or buy property.

## One-click setup

<table align="center">
  <tr>
    <td align="center" width="170">
      <a href="https://claude.ai/directory/connectors/assetfy"><img src="https://img.shields.io/badge/Claude-D97757?style=for-the-badge&logo=claude&logoColor=white" alt="Add to Claude"></a><br>
      <sub>Claude apps</sub>
    </td>
    <td align="center" width="170">
      <a href="https://cursor.com/en/install-mcp?name=Assetfy&config=eyJ1cmwiOiJodHRwczovL21jcC5hc3NldGZ5LmNvbS9tY3AifQ=="><img src="https://img.shields.io/badge/Cursor-000000?style=for-the-badge&logo=cursor&logoColor=white" alt="Add to Cursor"></a><br>
      <sub>Cursor</sub>
    </td>
    <td align="center" width="170">
      <a href="https://vscode.dev/redirect/mcp/install?name=Assetfy&config=%7B%22url%22%3A%22https%3A%2F%2Fmcp.assetfy.com%2Fmcp%22%2C%22type%22%3A%22http%22%7D"><img src="https://img.shields.io/badge/VS_Code-007ACC?style=for-the-badge" alt="Add to VS Code"></a><br>
      <sub>VS Code / Copilot</sub>
    </td>
  </tr>
</table>

After installing, sign in once with your Assetfy account. An [Assetfy account](https://assetfy.com/pricing/) with a PROFESSIONAL or ENTERPRISE plan is required.

### Claude Code

```bash
/plugin marketplace add assetfy-com/assetfy-ai-plugins
/plugin install assetfy@assetfy
```

Or add the server only: `claude mcp add --transport http assetfy https://mcp.assetfy.com/mcp`, then `/mcp` to sign in.

### Gemini CLI

```bash
gemini extensions install https://github.com/assetfy-com/assetfy-ai-plugins
```

Then `/mcp auth assetfy`.

### Antigravity

```bash
agy plugin install https://github.com/assetfy-com/assetfy-ai-plugins
```

Then authenticate under Agent settings → Customizations.

### ChatGPT and Codex

The plugin is in [`plugins/chatgpt`](plugins/chatgpt); the upload ZIP is under [Releases](https://github.com/assetfy-com/assetfy-ai-plugins/releases).

### Any other MCP client

```json
{
  "mcpServers": {
    "assetfy": { "type": "http", "url": "https://mcp.assetfy.com/mcp" }
  }
}
```

Streamable HTTP, OAuth 2.1 with dynamic client registration and PKCE.

## Example prompts

- "Erstelle mir einen Steckbrief zur Bebaubarkeit von Flurstück 44/11 in Hannover-List: GRZ, GFZ, Bodenrichtwert, Gebäude und Potenzial."
- "What may be built on the plot at Am Mittelhafen 11, 48155 Münster?"
- "Gibt es für den Punkt 50.62618, 6.94504 in Rheinbach einen Bebauungsplan? Zeig mir die Planunterlagen."
- "Wie steil ist das Flurstück an der Koordinate 50.62618, 6.94504 in Rheinbach, und in welche Richtung fällt es ab?"
- "Zeig mir das einfache 3D-Gebäudemodell rund um Am Mittelhafen 11 in Münster."
- "Wie viele HPC-Ladepunkte gibt es im Umkreis von 5 km um 51.9497, 7.6400 in Münster?"
- "Welches Flurstück liegt an der Koordinate 48.1986, 16.3417 in Wien?"

## What it covers

Data coverage and freshness per Bundesland: [assetfy.com/datenaktualitaet](https://assetfy.com/datenaktualitaet/). Each result also says which states it searched and where data is missing.

## Plans

| | PROFESSIONAL | ENTERPRISE |
|---|---|---|
| Parcel, planning, buildings, land value, terrain, 3D, listings | yes | yes |
| Site screening across many parcels (by use, size, Bebauungsplan, motorway access) | — | yes |
| Daily limit | 100 prompts per day | none |
| Site-plan export (DXF, PDF, IFC, GeoPackage) | 35 locations per month | unlimited |

Details and booking: [assetfy.com/pricing](https://assetfy.com/pricing/).

## Data and security

- **Read-only.** No tool creates, changes or deletes anything in Assetfy or in your account. Your own saved places and favourites can be read; saving happens in the Assetfy app.
- **What the server sees:** only the tool calls of your assistant with their parameters, such as an address or a parcel ID. The conversation, files and chat history do not reach the server.
- **Logging:** per tool call we log the tool name, the parameters (truncated to 1,000 characters), duration, response size, errors, the client ID and a pseudonymous user ID (shortened SHA-256 hash). Logs are kept for 30 days.
- **Access tokens** are checked against the Assetfy authorization server on every call (cached for at most 60 seconds). Disconnect assistants under [My account → KI MCP-Konnektor](https://assetfy.com/settings/mcp/); access ends within a minute.
- **Hosting:** the server runs in Frankfurt (Germany).
- **Plugins** in this repository contain no code: they add the server URL and a short skill that explains the tools.

Privacy policy: [assetfy.com/datenschutz](https://assetfy.com/datenschutz/) · Security reports: see [SECURITY.md](SECURITY.md).

## Support

Account, plan and data questions: hallo@assetfy.com. Plugin or connection problems: [open an issue](https://github.com/assetfy-com/assetfy-ai-plugins/issues/new/choose).
