# Connect Google Antigravity

You need Antigravity and a hub account with a role for the tools you need. Antigravity opens the Axle hub's Keycloak sign-in. There is no API key.

Remote servers use `serverUrl`. From the [Antigravity MCP docs](https://antigravity.google/docs/mcp/), streamable HTTP looks like this:

```json
{
  "mcpServers": {
    "axle": {
      "serverUrl": "https://mcp.axle.brightwire.ai/mcp"
    }
  }
}
```

Put that in `~/.gemini/config/mcp_config.json` (every project) or `.agents/mcp_config.json` (one project). Antigravity runs OAuth for the server. In settings, choose Authenticate next to `axle`, then finish the Keycloak page.

A `401` means authentication is required. When the session expires, authenticate again.

Then tell Antigravity:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
