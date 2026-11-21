# PPL for AI assistants

Connect an AI assistant to your PPL account so it can create and manage your
series and videos with you. This folder holds what an assistant needs:

- the PPL connector's address: `https://api.ppl.xyz/mcp`
- the official MCP Registry entry (`server.json`)
- the PPL skill (`plugins/ppl/skills/ppl/`), which teaches an assistant how
  PPL works: reading a series, writing a prompt, pricing it, rendering a
  draft, and what needs your say-so
- a Claude Code plugin and marketplace entry that install both together
- a Cursor configuration file

You approve each assistant in the PPL app, choose what it may do and how many
gems it may spend a day, and can disconnect it at any time in PPL › Settings ›
Connected Apps.

The skill and its tool list are generated from the PPL server
(`pnpm run build:connected-apps-skill` in ppl-backend). Do not edit them by
hand.

## Claude (claude.ai, desktop and mobile)

**[Add PPL to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=PPL&connectorUrl=https%3A%2F%2Fapi.ppl.xyz%2Fmcp%3Fref%3Dgithub)**:
the link opens Claude's "Add custom connector" dialog with PPL filled in.
Choose Add, sign in when asked, and approve the connection in the PPL app
(or on ppl.xyz with Google). Works on every Claude plan; the Free plan
allows one custom connector.

By hand: Customize › Connectors › "+ Add" › "Add custom connector", name
`PPL`, address `https://api.ppl.xyz/mcp`.

On a Team or Enterprise plan an owner adds it under Organization settings ›
Connectors.

Add the skill (optional, recommended): zip the `plugins/ppl/skills/ppl`
folder and upload it under Customize › Skills › "+" › "Create skill" ›
"Upload a skill", or install it with `npx skills add pplxyz/ppl-mcp`.

## Claude Code

```
/plugin marketplace add pplxyz/ppl-mcp
/plugin install ppl@ppl-xyz
```

The plugin adds the connector and the skill. Once connected, PPL's
workflows show up as slash commands named after the server, for example
`/mcp__ppl__next_episode`, `start_series`, `pilot_week`, `whats_working`
and `find_crossover`. Sign in from `/mcp` if Claude Code does not ask on
its own.

## Cursor

Copy `cursor/mcp.json` to `.cursor/mcp.json` in a project, or to
`~/.cursor/mcp.json` to use it everywhere, then sign in when Cursor asks.

## ChatGPT

In ChatGPT, add a custom MCP server with the address
`https://api.ppl.xyz/mcp` and sign in with OAuth. Where this setting lives
depends on your plan and may require developer mode.

## License

The files in this folder (the skill, the plugin and the configuration) are
MIT licensed: see `LICENSE`. The PPL service they connect to is not; using
it is subject to PPL's Terms (https://ppl.xyz/terms).
