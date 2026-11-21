---
name: rule-check
description: Check a finished clip against technical specs, campaign rules and banned content before posting. Use before every upload, or when the user asks "is this ok to post".
---

# Rule check

Run commands from the repository root. Read `AGENTS.md` first.

For a personal technical test:

`python scripts/check.py jobs/<id>/edits/clip_<n>.mp4`

This checks only the rules implemented by `check.py`. A PASS without
`--campaign` is not campaign approval.

For a campaign clip, first obtain the complete rules for ONE campaign
and save them in a separate file, for example
`<page-folder>/campaign-rules/<campaign-name>.md`.
Do not pass the combined `<page-folder>/campaigns.md` to `--campaign`.

The script recognizes these fields when present:

- `min_seconds: 15`
- `max_seconds: 60`
- `required_hashtags: #example`
- `required_mention: @example`

Then run:

`python scripts/check.py jobs/<id>/edits/clip_<n>.mp4 --campaign <rules-file> --caption "CAPTION TEXT"`

Review the campaign's full rules manually as well. The script does not
verify footage permission, required overlays, CTA wording, approval
process, or every prohibited-content rule. Mark those checks as
unverified until their requirements are available and reviewed.

Report each automated result and manual check separately. Do not say a
clip is campaign-ready when required rules or assets are missing.
Do not upload automatically.