# Axle MCP

Connect an IT operator assistant to the Axle hub.

| | |
|---|---|
| Server | `https://mcp.axle.brightwire.ai/mcp` |
| Transport | HTTP |
| Sign-in | The hub Google account you were given. A browser window opens. |
| Discovery | [`/.well-known/oauth-protected-resource`](https://mcp.axle.brightwire.ai/.well-known/oauth-protected-resource) |

Claude Code and Codex are the clients you can connect today. Use the client id that matches the app. The id is public. It is not a password.

After the tools appear, tell the assistant:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.

That guide is how to use the hub. It is available only after sign-in.

## Claude Code

```bash
claude mcp add --transport http --client-id claude-code --scope user axle https://mcp.axle.brightwire.ai/mcp
claude mcp login axle
```

Details: [docs/install-claude.md](docs/install-claude.md).

## Codex

```bash
codex mcp add axle --url https://mcp.axle.brightwire.ai/mcp --oauth-client-id codex
codex mcp login axle
```

Details: [docs/install-codex.md](docs/install-codex.md).

## What this repository is

Connection steps only. It does not describe tools, tenants, or anything inside the hub. Load that through the MCP after you sign in.
