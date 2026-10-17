# Assetfy

The `assetfy` MCP server answers questions about German and Austrian properties from official cadastral and planning data. Use it when the user names an address, a Flurstück (Gemarkung, Flur, Flurstücksnummer) or a property listing.

- Sign in once with `/mcp auth assetfy` (Assetfy account with a PROFESSIONAL or ENTERPRISE plan).
- A street address can go straight into the `address` parameter; no outside geocoding is needed.
- Start with `assetfy_get_parcel_profile` for one parcel: size, buildings, Bebauungsplan or §34/§35 BauGB, Bodenrichtwert. Go deeper only where the user asks.
- Answer in the user's language and keep the German legal terms: Flurstück, Gemarkung, Bebauungsplan, Bodenrichtwert, GRZ, GFZ, BGF, Traufhöhe, Firsthöhe.
- Building potential is an indicative first assessment, not a legal opinion or a building permit.
- All tools are read-only. Results carry `assetfy_url`, a link to the parcel on the Assetfy map.
