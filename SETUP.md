# Connect Foliyo

A Foliyo account is required. This plugin uses the hosted MCP server at https://foliyo.io/mcp over Streamable HTTP. It does not run a local server or require pasted API secrets.

1. Enable the plugin and connect its Foliyo MCP server using Claude's connection controls. In Claude Code, use `/mcp`, select Foliyo, and authenticate.
2. Sign in to the intended Foliyo workspace in the browser and review the requested OAuth permissions. Editing links created in other agents requires `workspace:write` alongside `mcp`. Let the user complete authentication; never request passwords, tokens or verification codes in chat.
3. Call `prepare_foliyo` to confirm connectivity and read account context and plan. Do not publish a test page merely to connect.
4. Ask the user for work to create or update. Follow the numbered questions returned by the server, skipping choices already supplied.

If authentication fails, explain the returned error and guide the user to reconnect. Do not weaken access settings, create a substitute account or publish anonymously. If Foliyo is already connected separately, use one intended connection and avoid duplicate tools.

Help: https://foliyo.io/support · Privacy: https://foliyo.io/privacy · Terms: https://foliyo.io/terms
