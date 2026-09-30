# Connect Google Antigravity

You need the Antigravity CLI or IDE, the deployment's MCP URL, and the account that deployment gave you. The usual client id is the one your operator registered for Antigravity. Axle does not use dynamic client registration, so the client id has to be in the config. There is no client secret.

Antigravity's remote MCP setting uses `serverUrl` (not `url`). From the [Antigravity MCP docs](https://antigravity.google/docs/cli/mcp/), a server without dynamic registration looks like this:

```json
{
  "mcpServers": {
    "axle": {
      "serverUrl": "https://mcp.example.com/mcp",
      "oauth": {
        "clientId": "antigravity"
      }
    }
  }
}
```

Replace the URL and the client id with the values for your deployment. Use the Interactive MCP Manager or the `mcp_config.json` path in those docs. A browser should open for that deployment's sign-in.

Antigravity's HTTP OAuth support is still catching up. Some versions complete the browser login and then call the server without the token, so the tools never appear. When that happens, connect with Claude Code, Codex, or Cursor instead. Those clients are the ones this guide treats as ready.

Then tell Antigravity:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
