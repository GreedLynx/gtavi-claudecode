---
name: secrets-map
description: Track and verify GTA 6 hidden spots, cars, collectibles, and easter eggs, then prepare post drafts. Use when the user asks about secrets or wants to scan a video for possible discoveries.
---

# Secrets map

Run commands from the repository root. Read `AGENTS.md` first.
Store the database in `<page-folder>/secrets.csv`.
A transcript match is a lead, not a verified game fact.

Entries live in `secrets.csv` (id, category, name, where, how, source_channel, source_url_with_timestamp, found_on, status, verified_by, notes). Categories: place, money, car, collectible, easter_egg, other. Status: unverified, verified, wrong.

## Commands

Put `--csv <page-folder>/secrets.csv` before the subcommand:

- Scan a job:
  `python scripts/secrets_map.py --csv <page-folder>/secrets.csv scan jobs/<id>`
- Add an entry manually:
  `python scripts/secrets_map.py --csv <page-folder>/secrets.csv add --name "NAME" --where "LOCATION" --how "STEPS" --category place --channel "CREATOR" --url "SOURCE_URL"`
- Mark an entry verified, only after checking the actual claim:
  `python scripts/secrets_map.py --csv <page-folder>/secrets.csv verify <id> --by "HOW AND WHEN VERIFIED"`
- Mark an incorrect entry:
  `python scripts/secrets_map.py --csv <page-folder>/secrets.csv wrong <id>`
- Generate post drafts:
  `python scripts/secrets_map.py --csv <page-folder>/secrets.csv posts --out <page-folder>/secrets-posts.md`
- Generate a tracking map:
  `python scripts/secrets_map.py --csv <page-folder>/secrets.csv map --out <page-folder>/secrets.md`

## Flow

1. Scan a transcribed GTA 6 video. Review the actual source moment
   and correct transcript errors before editing an entry.
2. Check each claimed location or item in the game or against reliable
   official material. Record how it was checked. Use `verify` only when
   the claim is substantiated; otherwise leave it `unverified` or mark
   it `wrong`.
3. Generate drafts from verified entries. Review the facts, source
   credit, and destination platform's rules manually.
   `scripts/check.py` requires an MP4; it cannot check a text-only draft.
4. Show the drafts to the user. Do not post automatically.

## Rules

1. Post verified entries only. Unverified is a lead, not a fact.
2. Credit the finder on every post (`🎥 channel` plus the timestamp link). Never present a creator's find as ours.
3. No glitches, exploits, money glitches, duplication, leaks or "play early" content. The script refuses them; do not work around it.
4. Scan output is a transcript guess. Rewrite the name, where and how by hand; do not post the raw quote.
5. No spoilers for story moments in launch week. Never imply the page is Rockstar. Use "GTA 6". X posts have no hashtags.
