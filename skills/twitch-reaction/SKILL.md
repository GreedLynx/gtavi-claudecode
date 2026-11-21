---
name: twitch-reaction
description: Create a reaction clip from an authorized Twitch stream or VOD, with the streamer above gameplay and a title between them. Use when the user asks for a Twitch reaction clip.
---

# Twitch reaction clips

Run commands from the repository root. Read `AGENTS.md` first.
Use a stream covered by a campaign whose rules are known, or one whose
creator has permitted the intended use. Credit alone is not permission.

## 1. Find a source

Read `skills/stream-finder/SKILL.md`. To search for live streams, run:

`python scripts/streams.py --query "gta 6"`

Check the relevant campaign in `<page-folder>/campaigns.md` and its
complete rules in a separate campaign rules file. Confirm that this
creator and source footage are allowed.

## 2. Find a moment

For a live stream, read `skills/live-mode/SKILL.md` before recording:

`python scripts/live.py https://twitch.tv/<login> --minutes 60`

Review a generated `jobs/<live-id>/live/spike_<n>.mp4`, then run
`moment-finder` on that file to create a new job with `candidates.json`.

For a finished VOD or clip, read `skills/moment-finder/SKILL.md` and run:

`python scripts/moments.py "<vod-or-local-file>" --top 8`

Use the job ID printed by `moments.py` for the next step.

## 3. Cut the reaction clip

Read `skills/hook-writer/SKILL.md` and verify the moment visually.
Write a title that describes what actually happened. Then run:

`python scripts/cut.py jobs/<id> --pick <n> --layout react --cam auto --title "VERIFIED TITLE" --title-style box --captions bubble`

Replace `<id>`, `<n>`, and the title with actual values. Inspect the
result at `jobs/<id>/edits/clip_<n>.mp4`.

The `react` layout requires a detectable streamer face and gameplay.
If detection fails, the script may skip the clip. Review its error;
choose another moment or correct the camera region rather than claiming
a reaction clip was created.

## 4. Check and report

Read `skills/rule-check/SKILL.md`. Check the finished clip against
the complete rules for that one campaign. Inspect the crop, title,
captions, audio, required assets, and caption credit manually.

Report the clip path, source, creator credit, campaign check results,
and any requirements still unknown. Do not upload automatically.