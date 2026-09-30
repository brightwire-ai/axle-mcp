# Axle MCP

Connect an assistant to an Axle deployment.

Axle speaks [remote MCP over HTTP](https://modelcontextprotocol.io). Each deployment has its own server URL. The server tells the client where to sign in. You use the account that deployment gave you. That may be a company Google account, a Microsoft account, or another provider. The browser shows the right page. This guide does not pick one.

| | |
|---|---|
| Server | The deployment's MCP URL. It ends in `/mcp`. |
| Transport | HTTP |
| Client id | A public id for your app, from the person who runs that deployment. Common ids are `claude-code`, `codex`, and `cursor`. There is no client secret. |
| Discovery | `https://<mcp-host>/.well-known/oauth-protected-resource` |

Set the URL once, then use it in every command below:

```bash
export AXLE_MCP_URL=https://mcp.example.com/mcp
```

Deployments you can use today are listed in [docs/deployments.md](docs/deployments.md).

## Clients

Any MCP client that can call an HTTP server and sign in with a pre-registered public client can connect. Axle does not use dynamic client registration, so the client needs the client id.

| App | Guide |
|---|---|
| Claude Code | [docs/install-claude.md](docs/install-claude.md) |
| Codex | [docs/install-codex.md](docs/install-codex.md) |
| Cursor | [docs/install-cursor.md](docs/install-cursor.md) |
| Google Antigravity | [docs/install-antigravity.md](docs/install-antigravity.md) |
| Another MCP client | [docs/install-other.md](docs/install-other.md) |

## After the tools appear

Tell the assistant:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.

That guide is how to work in the hub. It is available only after sign-in.

## If you are handing this to someone

Send them this repository, the MCP URL for their deployment, and the client id for the app they use. They sign in with the account you created for them in that deployment.

## What this repository is

Connection steps only. It does not describe tools or anything inside a hub. Load that through the MCP after sign-in.
