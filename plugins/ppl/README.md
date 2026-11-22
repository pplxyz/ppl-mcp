# PPL

PPL (ppl.xyz) is an app for making AI series and videos with characters you
create. This plugin connects Claude to your PPL account: it adds the PPL
connector and a skill that teaches Claude how PPL works, so it can read your
characters, series and world, write a prompt for a video model, tell you the
gem price, start an episode as a draft, follow the render, and manage your
series, world assets, collabs and drafts with you.

## What it can do

The connector has 70 tools, grouped by the switches you choose when you
approve the connection:

- **See (always on)** (23): Get account, Show PPL home, List characters, List series, Get series, List drafts, Get job, Look up PPL help, Get creation guide, Get episode ideas, Get quote, Get world, Show world, Get world asset ideas, Find collab partners, Check collab access, List collab requests, Get collab earnings, List standalone videos, Get draft prices, Get stats, Get earnings, Get the character draft.
- **Create** (21): Create episode or video, Create series, Save series, Discard draft, Add to world, Change a location or prop, Draw a new look, Save a drawn look, Bring in an image from a link, Ask the creator for images, Upload an image file, Draw new poster art, Retry a failed render, Edit a draft’s title and caption, Render a draft again, Edit a draft with a prompt, Extend a draft, Design a new character, Set choices on the character draft, Create the character, Discard the character draft.
- **Manage** (20): Rename world asset, Set current style, Undo last edit of a world asset, Claim a cast member, Remove from world, Update character settings, Update series details, Update selling and release settings, Delete series, Recast a series cast member, Edit a planned episode, Remove a planned episode, Plan one more episode, Rewrite the plan, Edit a published episode, Reorder episodes, Delete episode, Add a video to a series, Take a post off the feed, Hide a collab episode from a profile.
- **Collab** (4): Ask to collab with a character, Invite a character into a series, Answer a collab request, Cancel or end a collab.
- **Publish** (2): Publish draft, Release episode.

## Your control

- You approve the connection yourself, in the PPL app or in your browser on
  ppl.xyz (signing in with Google), choose which switches are on, and set
  how many gems it may spend a day.
- A video is made as a draft, and publishing is its own switch.
  Every switch the assistant asks for starts on, publishing included; you can turn any of them off before you connect, except seeing your account.
- You can change the switches or disconnect at any time in PPL › Settings ›
  Connected Apps.

## Install

- **Claude (web, desktop and mobile):** open
  [Add PPL to Claude](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=PPL&connectorUrl=https%3A%2F%2Fapi.ppl.xyz%2Fmcp%3Fref%3Dgithub), choose **Add**, then
  connect when asked.
- **Claude Code:** `/plugin install ppl --marketplace pplxyz/ppl-mcp`
  (Claude Code 2.1.275 or later; before that, `/plugin marketplace add
  pplxyz/ppl-mcp` then `/plugin install ppl@ppl-xyz`), then connect
  when asked.
- **Anything else that speaks MCP:** the connector address is
  https://api.ppl.xyz/mcp?ref=github.

This file, the skill and its tool list are generated from the PPL server's
own tool definitions. Do not edit them by hand.
