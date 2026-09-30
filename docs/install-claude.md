# Connect Claude Code

You need Claude Code, the deployment's MCP URL, and the account that deployment gave you. The usual client id is `claude-code`.

```bash
export AXLE_MCP_URL=https://mcp.example.com/mcp
claude mcp add --transport http --client-id claude-code --scope user axle "$AXLE_MCP_URL"
claude mcp login axle
```

`--scope user` keeps the server available in every project. A browser opens for that deployment's sign-in. When it finishes, Claude Code lists the Axle tools.

Check:

```bash
claude mcp get axle
```

The status should be connected. If it says authentication is required, run `claude mcp login axle` again.

Then tell Claude:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
