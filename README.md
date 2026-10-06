# Axle MCP

Connect an assistant to the Axle hub.

The hub hosts the MCP server. This repository is the connection guide.

## Connect

| | |
|---|---|
| URL | `https://mcp.axle.brightwire.ai/mcp` |
| Transport | Streamable HTTP |
| Auth | OAuth. The client opens the Axle hub's Keycloak sign-in. There is no API key to paste. |

Sign in with a hub account that has a role for the tools you need. The tools you see depend on the account you sign in with.

### Cursor

Add this to `~/.cursor/mcp.json` (every project) or `.cursor/mcp.json` (one project). A `url` entry is a remote server. Cursor uses OAuth for it.

```json
{
  "mcpServers": {
    "axle": {
      "url": "https://mcp.axle.brightwire.ai/mcp"
    }
  }
}
```

Restart Cursor and finish the sign-in it opens. In the Cursor CLI, after that file is saved:

```bash
agent mcp login axle
```

### Claude Code

```bash
claude mcp add --scope user --transport http axle https://mcp.axle.brightwire.ai/mcp
```

`--transport http` is how Claude Code selects streamable HTTP. `--scope user` keeps the server in every project. Finish the Keycloak sign-in in the browser, or run `claude mcp login axle`.

### Claude Desktop

Add a custom connector and set its remote MCP URL to `https://mcp.axle.brightwire.ai/mcp`. Leave the request headers empty. Choose sign-in, and finish the hub's Keycloak page. Steps are in [docs/install-claude-desktop.md](docs/install-claude-desktop.md).

### Another client

Use the same URL over streamable HTTP, and let the client run OAuth. There is no API key to paste. Claude Code accepts this JSON (`streamable-http` is an alias of `http`):

```json
{
  "mcpServers": {
    "axle": {
      "type": "http",
      "url": "https://mcp.axle.brightwire.ai/mcp"
    }
  }
}
```

## If sign-in fails

A `401` means authentication is required. Sign in again in the client. When the session expires, sign in again the same way.

The tool list follows the signed-in identity. Another hub role sees another set of tools.

## Clients

| App | Guide |
|---|---|
| Claude Code | [docs/install-claude.md](docs/install-claude.md) |
| Claude Desktop | [docs/install-claude-desktop.md](docs/install-claude-desktop.md) |
| Codex | [docs/install-codex.md](docs/install-codex.md) |
| Cursor | [docs/install-cursor.md](docs/install-cursor.md) |
| Google Antigravity | [docs/install-antigravity.md](docs/install-antigravity.md) |
| Another MCP client | [docs/install-other.md](docs/install-other.md) |

The hosted URL is also in [docs/deployments.md](docs/deployments.md).

## After the tools appear

Tell the assistant:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.

That guide is how to work in the hub. It is available only after sign-in.

## If you are handing this to someone

Send them this repository. They use the URL above and sign in with the hub account you gave them.

## What this repository is

Connection steps only. It does not describe tools or anything inside the hub. Load that through the MCP after sign-in.
