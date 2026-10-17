# Assetfy for Microsoft 365 Copilot

Microsoft 365 app package that registers the Assetfy MCP server (`https://mcp.assetfy.com/mcp`) as an agent connector. Copilot signs in to Assetfy through OAuth dynamic client registration; all tools are read-only.

## Build the package

`referenceId` is the ID of the dynamic client registration created in the [Teams Developer Portal](https://dev.teams.microsoft.com) for `https://mcp.assetfy.com/mcp`.

```bash
cd plugins/microsoft365
sed 's/${{ASSETFY_DCR_REFERENCE_ID}}/<reference-id>/' manifest.json > /tmp/manifest.json
zip -j assetfy-m365.zip /tmp/manifest.json color.png outline.png
```

The ZIP is uploaded in Partner Center (Microsoft 365 Copilot connector) or, for one organization, in the Microsoft 365 admin center.
