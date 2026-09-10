# Foliyo MCP

Create, brand, publish and track client-ready pages from your AI tools.

[Website](https://foliyo.io) · [Setup guide](https://foliyo.io/integrations)

Foliyo turns reports, proposals, research and updates into branded hosted pages. Choose a sender and a client design guide, publish a stable link, control access, update the page, and see engagement from your AI assistant.

This repository contains public connection configuration and a usage skill for Foliyo's hosted service.

## Connect

- **Server URL:** https://foliyo.io/mcp
- **Transport:** Streamable HTTP
- **Authentication:** OAuth with browser sign-in and PKCE. A Foliyo account is required.
- **Official MCP Registry name:** io.foliyo/foliyo

### Cursor

Install this plugin, or add the contents of mcp.json to your Cursor MCP configuration. Enable Foliyo and complete browser authorization.

### Codex

```sh
codex mcp add foliyo --url https://foliyo.io/mcp
codex mcp login foliyo --scopes 'mcp,workspace:write'
```

### Replit

[Add Foliyo to Replit](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkZvbGl5byIsImJhc2VVcmwiOiJodHRwczovL2ZvbGl5by5pby9tY3AifQ==)

Or open Integrations, add an MCP server, enter the server URL above, and sign in.

### Other clients

Use the same server URL in a client that supports remote Streamable HTTP MCP and OAuth. See the setup guide for Claude, ChatGPT, Windsurf and VS Code instructions and the standalone CLI. Client feature support varies.

## Try it

> Create a Foliyo for this client proposal. Use the client's website as the design reference.

> Update that Foliyo with the revised timeline.

> Which of my Foliyos have been read?

The assistant can clarify the content, sender, design reference and audience before publishing. Ask for numbered choices when choosing between options.

## Plans

Free includes unlimited published pages, basic view counts, PIN protection and Foliyo branding. Pro is $29/month or $290/year per workspace, with additional branding, access and engagement features. No per-seat pricing. Current product limits and features are documented on the website.

## Authentication notes

Tool discovery is public so directories can inspect capabilities. Private data and tool execution require authorization. Never place access tokens or client data in this repository or a public listing.
