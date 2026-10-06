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

### Claude plugin

This repository bundles a Claude skill and the hosted Foliyo MCP connection. Public directory review is separate from installing it directly; no Anthropic verification or featured placement is claimed.

For Claude Code, install from this repository's marketplace:

```text
/plugin marketplace add jooliperbush/foliyo-mcp
/plugin install foliyo@foliyo
```

Then use `/mcp` to authenticate the Foliyo connection. See [setup instructions](SETUP.md). For Claude's web/desktop app, use its custom connector at `https://foliyo.io/mcp` and upload the [Foliyo skill](skills/foliyo/SKILL.md) where supported until directory installation is available.

Try: “Create a Foliyo from this proposal.” The skill asks about format, audience, brand, sender and access, reusing choices already supplied. Available HTML formats include scrolling pages, fixed 16:9 slides and flexible slides. This is not a PowerPoint export or arbitrary JavaScript hosting service.

Detailed readership analytics and email gates require Foliyo Pro. A shared PIN does not identify readers; personal links attribute activity to the named recipient but can be forwarded. Notification email is opt-in. Work submitted to publishing tools is stored by Foliyo; read the [privacy policy](https://foliyo.io/privacy) and [terms](https://foliyo.io/terms).

The integration source is MIT licensed. The hosted service is subject to its own terms and plan limits. Support: hello@foliyo.io.

### Cursor

Use the **Add to Cursor** button on the [Foliyo community listing](https://cursor.directory/plugins/foliyo), or merge the `foliyo` entry from [mcp.json](mcp.json) into your Cursor MCP configuration, preserving any existing servers. Enable Foliyo and complete browser authorization.

The community listing and the official Cursor Marketplace are separate. An official Marketplace application was received on 14 September 2026; approval and an official listing remain unconfirmed as of 6 October 2026. The public plugin package includes both the hosted MCP configuration and the [Foliyo skill](skills/foliyo/SKILL.md). Installing only the MCP configuration does not install the skill.

Plugin support: hello@foliyo.io. [Privacy](https://foliyo.io/privacy) · [Terms](https://foliyo.io/terms). A Foliyo account is required; Free and Pro plan details are below.

### Codex

```sh
codex mcp add foliyo --url https://foliyo.io/mcp
codex mcp login foliyo --scopes 'mcp,workspace:write'
```

### Replit

[Add Foliyo to Replit](https://replit.com/integrations?mcp=eyJkaXNwbGF5TmFtZSI6IkZvbGl5byIsImJhc2VVcmwiOiJodHRwczovL2ZvbGl5by5pby9tY3AifQ==)

Or open Integrations, add an MCP server, enter the server URL above, and sign in.

### Gemini CLI

Install the hosted MCP connection and Foliyo skill:

```sh
gemini extensions install https://github.com/jooliperbush/foliyo-mcp
```

Restart Gemini CLI, then run `/mcp auth foliyo` to sign in. Ask Gemini to create a Foliyo from your work. This extension is for Gemini CLI; Gemini web app availability and custom app setup are separate.

### Cline

See [Cline installation instructions](llms-install.md). Use the hosted endpoint with `type: "streamableHttp"`; preserve existing MCP servers when adding Foliyo.

### Grok Build

This repository includes a Grok Build plugin manifest, the Foliyo skill, and a hosted MCP connection. Official marketplace inclusion requires review and is not yet approved.

To connect the hosted server directly:

```sh
grok mcp add --transport http foliyo https://foliyo.io/mcp
grok mcp doctor foliyo
```

Complete the browser sign-in when Grok requests authorization. Use `/mcps` to inspect the connection. This is Grok Build setup, not a listing in Grok chat's connector catalog.

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

## Plugin distribution and data access

The connection configuration and instructions in this repository are MIT licensed, consistent with the Foliyo CLI package. This does not license the hosted application or grant rights to Foliyo trademarks. The hosted service is governed by [Foliyo terms](https://foliyo.io/terms) and [privacy policy](https://foliyo.io/privacy).

This plugin calls `https://foliyo.io/mcp` for authenticated tool operations and Foliyo's advertised OAuth endpoints on `https://foliyo.io` for sign-in. Published pages are served under `*.foliyo.io`. It contains no shell hooks, installers, local server executable or telemetry. The agent sends document content and selected branding, recipients and sharing settings when the user requests a publish or update; reports return workspace data. Notification email and deletion require explicit user requests. OAuth grants `mcp` and, for cross-client updates, `workspace:write`. Credentials stay in the client's credential storage. Do not include credentials in published pages, skill files or public submissions.

Maintained by Foliyo through the `jooliperbush` GitHub account, which owns this public integration repository. Contact: hello@foliyo.io.
