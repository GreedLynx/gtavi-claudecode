---
name: live-mode
description: Record an authorized live YouTube or Twitch stream, detect chat spikes, and create candidate clips. Use when the user asks to monitor a specific live stream.
---

# Live mode

Run commands from the repository root. Read `AGENTS.md` first.
Start recording only for a stream the user has selected and whose usage permission or applicable campaign terms have been checked.

Run:

`python scripts/live.py <youtube-or-twitch-live-url> --minutes 60`

The script stores recording segments in `jobs/<id>/live/` and writes detected moments to `jobs/<id>/live/spikes.md`. Candidate cuts are `jobs/<id>/live/spike_<n>.mp4`; they are not finished vertical clips.

Before starting:

1. Confirm the stream is public and not a leak, pirated copy or "play early" content. If unsure, do not start.
2. Note the streamer's handle for credit.

While it runs:

1. Review each detected spike against the video. Skip irrelevant
   moments, spoilers, and content prohibited by the campaign.
2. For a selected `spike_<n>.mp4`, read
   `skills/moment-finder/SKILL.md` and run `scripts/moments.py`
   on that file. Use the new job ID printed by `moments.py`.
   Then read `skills/hook-writer/SKILL.md` and
   `skills/clip-cutter/SKILL.md` to make the finished vertical clip.
3. Read `skills/rule-check/SKILL.md`. Report automated results and
   manually checked campaign requirements separately.
4. Show the user up to three reviewed clips with their file paths,
   captions, source links, and creator credits. Do not upload them.

When done, list the recording location, detected spikes, and finished clips separately. Read `skills/learning-loop/SKILL.md` to log a post only after the user confirms that it was actually posted. If no chat spike was detected, report that result; do not claim a clip was made.
