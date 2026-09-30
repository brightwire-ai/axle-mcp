# Connect Cursor

You need Cursor, the deployment's MCP URL, and the account that deployment gave you. The usual client id is `cursor`. Ask the person who runs the deployment to confirm that id is enabled before you rely on it.

Add this to `~/.cursor/mcp.json` (every project) or `.cursor/mcp.json` (one project). Leave the client secret out. Axle's clients are public.

```json
{
  "mcpServers": {
    "axle": {
      "url": "https://mcp.example.com/mcp",
      "auth": {
        "CLIENT_ID": "cursor"
      }
    }
  }
}
```

Replace the URL with your deployment's MCP URL. Reload Cursor, open the MCP settings for `axle`, and choose the sign-in action. A browser opens for that deployment's sign-in.

In the Cursor CLI, after the server is in `mcp.json`:

```bash
agent mcp login axle
```

Then tell Cursor:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
