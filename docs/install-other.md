# Connect another MCP client

Use this for any other MCP client that can call a remote HTTP server and sign in with OAuth.

You need a hub account with a role for the tools you need. The client opens the Axle hub's Keycloak sign-in. There is no API key to paste.

In the app's remote MCP settings:

- Transport: streamable HTTP.
- URL: `https://mcp.axle.brightwire.ai/mcp`.
- Auth: OAuth, handled by the client.

Clients that share Claude Code's JSON shape use `type` `http`. Claude Code also accepts `streamable-http` as an alias:

```json
{
  "mcpServers": {
    "axle": {
      "type": "http",
      "url": "https://mcp.axle.brightwire.ai/mcp"
    }
  }
}
```

A browser opens. Sign in with your hub account. A `401`, or a session that has expired, means sign in again. The tools that appear are the ones that account's role includes.

When the tools appear, say:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
