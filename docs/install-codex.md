# Connect Codex

You need the Codex CLI, the deployment's MCP URL, and the account that deployment gave you. The usual client id is `codex`.

```bash
export AXLE_MCP_URL=https://mcp.example.com/mcp
codex mcp add axle --url "$AXLE_MCP_URL" --oauth-client-id codex
codex mcp login axle
```

A browser opens for that deployment's sign-in. When it finishes, start Codex and ask it to use the Axle tools.

Check:

```bash
codex mcp get axle
```

If sign-in did not finish, run `codex mcp login axle` again.

Then tell Codex:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
