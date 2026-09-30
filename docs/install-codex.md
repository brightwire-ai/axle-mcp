# Connect Codex

You need the Codex CLI and the hub Google account you were given.

```bash
codex mcp add axle --url https://mcp.axle.brightwire.ai/mcp --oauth-client-id codex
codex mcp login axle
```

A browser opens for the hub Google sign-in. When it finishes, start Codex and ask it to use the Axle tools.

Check:

```bash
codex mcp get axle
```

If sign-in did not finish, run `codex mcp login axle` again.

Then tell Codex:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
