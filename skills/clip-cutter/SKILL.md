---
name: clip-cutter
description: Cut a picked moment into a 1080x1920 vertical clip with captions and a hook. Use after moment-finder or when the user asks to make a clip.
---

# Clip cutter

Run all commands from the repository root.

Before running:
1. Read `skills/hook-writer/SKILL.md`.
2. Prepare three hook options and select one that accurately describes the moment.

Run:

`python scripts/cut.py jobs/<id> --pick <n> --layout <layout> --hook "HOOK TEXT"`

For a technical test with an inaccurate transcript, add `--captions none`.
For a real clip, correct inaccurate transcript words before rendering captions.

Replace `<id>` and `<n>` with the selected job and moment. Replace
`<layout>` with one of:
- `fill`: crop gameplay to fill the frame.
- `blur`: center the full video over a blurred background.
- `facecam`: show gameplay and the streamer's camera for a reaction clip.

After running:
1. Find the MP4 at `jobs/<id>/edits/clip_<n>.mp4`. Check its resolution,
   hook timing, captions if enabled, audio, and ending.
2. For a campaign clip, read `skills/rule-check/SKILL.md` and check it
   against the applicable campaign rules. If the rules are unavailable,
   report that the campaign check is incomplete.
3. For a personal test clip, report the technical checks. Do not claim
   that it passes campaign rules.
4. Fix any observed problem and cut again if needed.
5. Show the user the finished file, suggested caption, creator credit
   when applicable, and check results. Do not upload it automatically.