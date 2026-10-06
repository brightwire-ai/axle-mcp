# Connect Claude Code

You need Claude Code and a hub account with a role for the tools you need. Claude Code opens the Axle hub's Keycloak sign-in. There is no API key.

```bash
claude mcp add --scope user --transport http axle https://mcp.axle.brightwire.ai/mcp
claude mcp login axle
```

`--transport http` selects streamable HTTP. `--scope user` keeps the server available in every project. A browser opens for the hub's Keycloak sign-in.

Check:

```bash
claude mcp get axle
```

If it says authentication is required, run `claude mcp login axle` again. A `401`, or a session that has expired, means the same thing: sign in again.

Then tell Claude:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
