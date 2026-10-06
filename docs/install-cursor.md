# Connect Cursor

You need Cursor and a hub account with a role for the tools you need. Cursor opens the Axle hub's Keycloak sign-in. There is no API key.

Add this to `~/.cursor/mcp.json` (every project) or `.cursor/mcp.json` (one project):

```json
{
  "mcpServers": {
    "axle": {
      "url": "https://mcp.axle.brightwire.ai/mcp"
    }
  }
}
```

A `url` entry is a remote server, and Cursor uses OAuth for streamable HTTP. Restart Cursor and finish the sign-in it opens.

In the Cursor CLI, after the server is in `mcp.json`:

```bash
agent mcp login axle
```

A `401` means authentication is required. When the session expires, run that login again.

Then tell Cursor:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
