---
name: questions-to-posts
description: Turn repeated fan questions (Reddit threads and comments on our own posts) into HOW TO post drafts. Use when the user asks what people are asking, wants HOW TO ideas, or says to turn comment questions into posts.
---

# Questions to posts

Run commands from the repository root. Read `AGENTS.md` first.
Use files inside the selected page folder for facts, ideas, and output.

Finds the questions fans keep asking, checks whether `facts.md` answers them, and drafts HOW TO posts from verified facts only.

## Command

Run from the repository root:

`python scripts/questions.py --subs GTA6,GTA,GrandTheftAutoV --days 3 --facts <page-folder>/facts.md --ideas <page-folder>/idea-bank.md --out <page-folder>/questions.md`

If the user has supplied comments from their own posts, add
`--comments <page-folder>/comments.txt`. Do not add that option if
the file does not exist.

## What you get

- `questions.md`: clusters ranked by count then upvotes. Each has the canonical question, count, example links, and either `answer found in facts.md: <line>` or `UNANSWERED: needs an official source`.
- Below the clusters: a HOW TO draft per answered cluster, in the playbook template (`HOW TO [DO THE THING] IN GTA 6`, numbered steps).
- `idea-bank.md`: every unanswered cluster is appended as a research task.

## After the run

1. Read each draft. The script copies steps from `facts.md` lines; it
   cannot judge order or whether a line is really a step. Fix the order
   and keep the wording true to the fact. A keyword match is only a
   candidate answer: confirm that the fact actually answers the question.
2. For each unanswered cluster, find an official source and add it to `facts.md` with the link, then rerun.
3. Review each draft against its linked official sources and the
destination platform's rules. `scripts/check.py` checks video files;
it cannot validate a text-only post. Show the draft to the user.
Do not post it automatically.

## Rules

1. Facts only from official sources (Rockstar, Take-Two, PlayStation, Xbox), logged in `facts.md` with the link. Recheck anything older than 48 hours.
2. Never invent steps, numbers, dates or menu names. No source, no step. An unanswered question stays a research task.
3. No leaks, rumors, piracy, exploits or "play early" tricks, even if fans ask for them. Skip those clusters.
4. Credit: if a post builds on a fan's clip or find, credit with `🎥 @creator`. Do not quote or name Reddit users; the questions are only a signal of what to cover.
5. Never imply the page is Rockstar. Use "GTA 6".
6. Keep all-caps to the hook line only.
