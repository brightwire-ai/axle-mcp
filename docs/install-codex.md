# Connect Codex

You need the Codex CLI and a hub account with a role for the tools you need. Codex opens the Axle hub's Keycloak sign-in. There is no API key.

```bash
codex mcp add axle --url https://mcp.axle.brightwire.ai/mcp
codex mcp login axle
```

That URL is a streamable HTTP server. OAuth is the login Codex uses for it. A browser opens for the hub's Keycloak sign-in. When it finishes, start Codex and ask it to use the Axle tools.

Check:

```bash
codex mcp list
```

A `401`, or a session that has expired, means run `codex mcp login axle` again.

Then tell Codex:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
