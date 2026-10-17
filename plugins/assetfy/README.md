# Assetfy

Official real estate data for Germany and Austria in your AI assistant. Ask in plain language about an address, a Flurstück (Gemarkung, Flur, Flurstücksnummer) or a property listing, and get the answer from the official cadastre and planning data.

## What it provides

- Flurstück on the cadastral map: size, outline, shape, street frontage, actual land use
- Buildings with function, storeys, Traufhöhe and Firsthöhe from the 3D building model (LoD2)
- Planning law: Bebauungsplan with plan documents, §34/§35 BauGB, an indicative GRZ/GFZ/BGF assessment
- Bodenrichtwert (official land value)
- Terrain from the 1 m elevation model, 3D building models, official aerial images
- Property listings for sale, matched to their Flurstück
- Your own saved places and favourites from your Assetfy account

## What the plugin runs and sends

The plugin contains no code. It adds one remote MCP server, `https://mcp.assetfy.com/mcp`, operated by Assetfy, and a `get-started` skill that explains how to use it. Tool calls with their parameters (for example an address or a parcel ID) are sent to that server; nothing else from the conversation is sent. All tools are read-only: nothing is created, changed or deleted in Assetfy or in your account.

## Requirements

An Assetfy account with a PROFESSIONAL or ENTERPRISE plan. On first use you sign in with your Assetfy account (OAuth 2.1).

## Links

- Setup and examples: https://assetfy.com/produkt/ai-mcp-anbindung/
- Privacy policy: https://assetfy.com/datenschutz/
- Support: hallo@assetfy.com
