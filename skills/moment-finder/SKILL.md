---
name: moment-finder
description: Find the best clip moments in a long video, stream VOD or local file. Use when the user gives a YouTube URL or video file and wants highlights, "find the moments", or candidates to cut.
---

# Moment finder

Run commands from the repository root. Read `AGENTS.md` first.
Use a source whose usage permission has been established. Do not assume
that a video appearing in `trends.md` is licensed for clipping.

Run:

`python scripts/moments.py <url-or-file> --top 8`

It writes `jobs/<id>/candidates.md`. Signals used: transcript with word timestamps (faster-whisper), loudness spikes, the YouTube "most replayed" heatmap and live-chat spikes, when available. A missing signal is skipped, not faked.

Then:

1. Read `jobs/<id>/candidates.md` and show each candidate: number, start-end, length, why it scored, transcript line.
2. Drop spoilers for story moments in launch week, nudity, and anything that looks like a leak.
3. Recommend the best 3 and say what hook angle each suggests.
4. For a selected candidate, read `skills/hook-writer/SKILL.md`
    and `skills/clip-cutter/SKILL.md`. Pass the actual candidate number
    as `--pick <n>` when cutting.

Record the source link and creator in `media/raw` notes. Credit the creator in the post caption.
