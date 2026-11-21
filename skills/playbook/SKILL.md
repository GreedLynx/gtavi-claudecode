---
name: playbook
description: Run the daily GTA 6 page routine from the full playbook. Use when the user says "daily routine", "what do I do today", "run the page", asks about the 7-day kickoff, launch day, content pillars, posting slots, or safety rules.
---

# Playbook

Run commands from the repository root. Read `AGENTS.md` first.
Use `<page-folder>` for all page-specific files.

1. Read `<page-folder>/playbook.md` if it exists. Otherwise read
   `skills/playbook/references/playbook.md`.
2. If the page folder does not exist, read
   `skills/setup/SKILL.md` and set up the page workspace first.
3. Check `<page-folder>/log.md` and
   `<page-folder>/scoreboard.csv` to determine the current stage.
4. Run the day:
   - Check current official sources. Record verified facts with links in
     `<page-folder>/facts.md`.
   - Before each workflow, read its file in `skills/<name>/SKILL.md`.
     Use `campaign-finder`, `trend-radar`, and `stream-finder` as needed.
   - Use `moment-finder`, `hook-writer`, and `clip-cutter` for an eligible
     source. Check usage permission and complete campaign rules first.
   - Use `rule-check` for each finished clip. Report automated and manual
     checks separately.
   - Use `learning-loop` only with real post and metric data.
5. Show the user each prepared clip with its file path, caption, source,
   creator credit, and any unresolved checks. Do not upload automatically.
6. End with a report separating prepared clips from posts the user
   confirms were published. Report metrics and payouts only when known.

Hard rules: no leaks, no "play early", no piracy, no GTA Online money or AFK bots, no invented facts or numbers, credit every creator, no earnings promises.
