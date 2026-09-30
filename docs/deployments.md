# Deployments

Replace `AXLE_MCP_URL` in the install guides with the URL for the deployment you are joining.

| Deployment | MCP URL |
|---|---|
| Brightwire hub | `https://mcp.axle.brightwire.ai/mcp` |

Sign-in is whatever that deployment uses. Open the client, and the browser shows its page. For the Brightwire hub today:

```bash
export AXLE_MCP_URL=https://mcp.axle.brightwire.ai/mcp
```

The server publishes its sign-in details at [`/.well-known/oauth-protected-resource`](https://mcp.axle.brightwire.ai/.well-known/oauth-protected-resource).

A new deployment is another row in this table: a host, the same `/mcp` path, and the account that deployment issues. The install commands stay the same.
