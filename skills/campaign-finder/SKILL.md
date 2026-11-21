---
name: campaign-finder
description: Find live GTA 6 and gaming clipping campaigns on Whop Content Rewards and record them. Use when the user asks where to earn, which campaigns are open, what the pay per 1K views is, or to refresh campaigns.md.
---

# Campaign finder

Read pages live. Do not rely on memory; payouts and budgets change daily.
Run commands from the repository root. Read `AGENTS.md` before starting.
Use live sources for campaign details; do not rely on remembered rates,
budgets, or rules.

1. Check these sources, using the browser tools or by fetching the pages:
   - Whop Content Rewards: `https://whop.com/discover/` (search "GTA 6", "GTA VI", "gaming clipping", "content rewards") and the public campaign pages on `https://contentrewards.com/` (campaign links look like `contentrewards.com/c/campaigns/<id>`).
   - Clip (Clip Tech, LLC): `https://www.clip.tech/clippers` lists live campaigns with the rate per 1K views and the share of budget left, without login. The campaign briefs and rules live in their Discord, so ask the human to paste them. Their terms say payouts are Net 30 after a campaign ends and depend on the client paying; tell the human this in one line.
2. For each campaign that looks live, open its page and record:
   - name and creator or brand
   - platforms accepted
   - rate per 1K views (and any cap per clip or per person)
   - budget left or total budget
   - key rules: allowed source content, minimum length, required credit, hashtags, banned content, approval process
   - link
   - date checked
3. Write or update a row per campaign in `<page-folder>/campaigns.md`,
   where `<page-folder>` is the workspace created by the setup skill.
   If more than one page folder exists, identify the intended page first.
   If a value is not visible, write `unknown`. Never estimate or invent a number.
4. If rules are behind a login, tell the user which campaign needs them
   and ask them to provide the rules text. Save it under that campaign in
   `<page-folder>/campaigns.md`. Do not join or accept terms for the user.
5. Skip any campaign that asks for leaks, "play early", piracy, GTA Online money or AFK bots, or fake accounts. Say why in one line.
6. Report a short ranked list: campaign, rate, budget left, effort. No earnings promises: pay depends on approved views and each campaign's own rules.
For each campaign, include its source link and the date checked.
Mark fields that cannot be verified as `unknown`. Do not treat a campaign
as usable until its allowed footage and posting rules are known.

The human joins campaigns and submits clips. You prepare and check the clips.
