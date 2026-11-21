---
name: stream-finder
description: Find live GTA 6 streams on YouTube and Twitch, ranked by concurrent viewers. Use when the user asks who is streaming now, wants live moments to clip, or before live-mode.
---

# Stream finder

Run commands from the repository root. Read `AGENTS.md` first.
Report the time checked and use only viewer counts returned by the script.

Run:

`python scripts/streams.py --query "gta 6"`

Then:

1. Show up to 10 relevant live streams from the actual script output:
    platform, channel, title, concurrent viewers, link, and time checked.
    Keep YouTube and Twitch counts separate; do not add viewer counts
    together for a creator streaming on both platforms.
2. Skip streams that are clearly leaks, early-access tricks or pirated copies. Say why in one line.
3. Recommend 1 to 3 streams that fit the page's niche. State whether
    permission to use each stream is known, unknown, or provided by an
    applicable campaign.
4. For an eligible live stream, offer `skills/live-mode/SKILL.md` as the
    next step. For a finished VOD, offer `skills/moment-finder/SKILL.md`.
    Check the source and its usage permission before recording or cutting.

Viewer counts are what the script returns at that moment. Do not guess or round them up.
