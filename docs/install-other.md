# Connect another MCP client

Use this when the app is not Claude Code, Codex, Cursor, or Antigravity. Gemini CLI, VS Code, Windsurf, Zed, and later clients all land here when they speak remote MCP.

You need three things from the person who runs the deployment:

1. The MCP URL, ending in `/mcp`.
2. The public client id they registered for your app.
3. An account on that deployment's sign-in page.

In the app's remote MCP settings:

- Transport: HTTP (streamable HTTP, not a local command).
- URL: the deployment MCP URL.
- OAuth client id: the id you were given.
- Client secret: leave empty.
- Scopes: leave empty so the client can read them from the authorization server.

The client should discover the sign-in server from:

```text
https://<mcp-host>/.well-known/oauth-protected-resource
```

A browser opens. Sign in with the account that deployment gave you. When the tools appear, say:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.

If the app can only register itself dynamically and has no field for a client id, it cannot connect. Axle uses a pre-registered public client for each app.
