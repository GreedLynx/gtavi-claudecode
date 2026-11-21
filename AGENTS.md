# GTA VI Clip Desk — Codex instructions

## Project layout

- `scripts/` contains the Python programs.
- `skills/<name>/SKILL.md` contains instructions for each workflow.
- `requirements.txt` contains Python dependencies.
- Run commands from the repository root unless a script explicitly requires another directory.

## Working method

1. Read the relevant `skills/<name>/SKILL.md` before starting a workflow.
2. If a skill refers to another skill, read that skill's `SKILL.md` before using it.
3. Replace example placeholders such as `<id>`, `<n>`, and `<layout>` with actual values. Do not pass the placeholders literally.
4. Inspect command output and generated files. Report errors instead of claiming a step succeeded.
5. Use current sources for live streams, trends, campaigns, rates, budgets, and platform rules. Mark unavailable information as unknown; do not guess.

## Clip workflow

1. Check the source video and whether it may be used.
2. Find and review candidate moments.
3. Write hooks that accurately describe the selected moment.
4. Cut the clip using the appropriate layout.
5. Check the resulting file and applicable campaign rules.
6. Give the user the file, suggested caption, creator credit, and check results.

## Publishing and claims

- Do not upload, post, submit, or join a campaign on the user's behalf unless the user explicitly asks.
- Do not treat creator credit as permission to use footage.
- Do not invent game facts, quotations, campaign terms, payouts, or permissions.
- Do not use leaks, pirated material, or misleading claims.
- Explain when a rule cannot be checked because its source is unavailable or requires login.

## Claude Code references

The `.claude-plugin/` directory is metadata for Claude Code. Codex does not use
its `/plugin` installation commands. When a skill mentions
`${CLAUDE_PLUGIN_ROOT}`, resolve the corresponding path from this repository root.