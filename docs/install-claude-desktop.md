# Connect Claude Desktop

You need Claude Desktop and a hub account with a role for the tools you need. Claude opens the Axle hub's Keycloak sign-in. There is no API key.

On a Pro or Max plan:

1. Open Customize, then Connectors.
2. Choose Add, then Add custom connector.
3. Name it `axle`.
4. Set the remote MCP URL to `https://mcp.axle.brightwire.ai/mcp`.
5. Review the authentication settings Claude detected.
6. Choose Sign in now, or Sign in when needed.
7. On the OAuth client step, use Claude's published identity.
8. Leave the request headers empty.
9. Finish the hub's Keycloak page.

On a Team or Enterprise plan, an owner adds the connector under Organization settings, then Connectors: Add, Custom, then Web, with the same URL and sign-in. You then open Customize, then Connectors, and connect `axle`.

A `401`, or a session that has expired, means connect the connector again and finish sign-in.

Then tell Claude:

> Call `repos_list`, then `docs_list` and `docs_read`, and follow the operator guide you find.
