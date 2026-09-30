# Connect Claude Code

You need Claude Code and the hub Google account you were given.

In a terminal, outside the Claude prompt:

```bash
claude mcp add --transport http --client-id claude-code --scope user axle https://mcp.axle.brightwire.ai/mcp
claude mcp login axle
```

`--scope user` keeps the server available in every project. A browser opens for the hub Google sign-in. When it finishes, Claude Code lists the Axle tools.

Check:

```bash
claude mcp get axle
```

The status should be connected. If it says authentication is required, run `claude mcp login axle` again.

Then tell Claude:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
