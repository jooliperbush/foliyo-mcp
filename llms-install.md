# Install Foliyo in Cline

Foliyo is a hosted MCP service. Do not clone a server, start a local web application, or deploy anything. A Foliyo account is required.

1. Open Cline's MCP Servers panel and choose Remote Servers.
2. Use name `foliyo`, URL `https://foliyo.io/mcp`, and transport **Streamable HTTP**.
3. Complete Foliyo browser authorization if offered by the client. Otherwise sign in to https://foliyo.io/keys and create a workspace publish key. Put it only in the local Cline configuration's Authorization header. Never post the key in a chat transcript, repository, issue or listing.
4. For manual configuration, merge this entry with the existing `mcpServers` entries, preserving other servers:

```json
{
  "mcpServers": {
    "foliyo": {
      "type": "streamableHttp",
      "url": "https://foliyo.io/mcp",
      "headers": {
        "Authorization": "Bearer YOUR_FOLIYO_WORKSPACE_KEY"
      },
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

Use the header only for the workspace-key option. Replace the placeholder privately with the user's own Foliyo key. In Cline CLI 3.0.61, the active configuration is `<data-dir>/settings/cline_mcp_settings.json` when using `--data-dir`; the default storage resolves to `~/.cline/data/settings/cline_mcp_settings.json`. This version did not load the project-local `.cline/mcp.json` in our test. In the IDE, use MCP Servers > Configure > Configure MCP Servers to locate the active file. Check the installed version rather than assuming the same file path across Cline releases.

The exact transport spelling matters: `streamableHttp`. Omitting it can select legacy SSE, which Foliyo does not serve.

5. Confirm tools appear and ask: "Read my Foliyo brand guide without changing anything." Confirm the result matches the intended workspace.
6. Test publishing only with the user's approval and fictional content. Start with `prepare_foliyo`, then `preflight_html`, then `publish_html`. Keep email notifications off unless explicitly requested. Return the actual share URL and generated PIN.

A Free account supports basic publishing and PIN access. Pro features require Pro on the connected workspace. Do not describe a successful remote connection as a public marketplace listing.

Support: https://foliyo.io/support
