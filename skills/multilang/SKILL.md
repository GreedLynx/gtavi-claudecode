---
name: multilang
description: Turn one finished clip into localized versions (Spanish, Portuguese, German, Russian and more) with translated word-by-word captions, translated hook, optional stock voiceover of the hook, and per-platform captions. Use when the user says "translate the clip", "make it in Spanish", "other languages", "localize", "5 languages".
---

# Multilang

Run commands from the repository root. Read `AGENTS.md` first.
Read `skills/clip-cutter/SKILL.md` and verify that the original clip,
its hook, and its transcript are accurate before translating.

The script uses `jobs/<id>/transcript.json` even if the original clip
was cut with `--captions none`. Correct transcript errors before using
the localized MP4 files. Review all translated hooks and captions.
Add creator credit manually where required; generated captions do not
fill it in. Check generated hashtags against the actual video topic
and the applicable campaign rules.

Non-English GTA pages are underserved, so one clip can feed several audiences.

Run after `clip-cutter` (the clip must already exist as `jobs/<id>/edits/clip_<n>.mp4` + `.json`):

`python scripts/translate.py jobs/<id> --pick <n> --langs es,pt,de,ru`

Output in `jobs/<id>/edits/`: `clip_<n>_<lang>.mp4` per language and one `clip_<n>_captions.md` with X, Instagram and TikTok/Shorts captions per language.

- Review the rendered layout, hook, captions, and audio in every language.
  `translate.py` supports `fill`, `blur`, and `facecam` layouts; it does
  not support `react`. Do not claim a `react` clip was localized
  successfully without a separately verified rendering workflow.
- `--voice` adds a stock text-to-speech voice (edge-tts: es-ES-AlvaroNeural, pt-BR-AntonioNeural, de-DE-ConradNeural, ru-RU-DmitryNeural) that reads the translated hook only, in the first 2.5 seconds, with the original audio ducked under it.
- Never clone or imitate a real person's or streamer's voice. Stock voices only, and do not present the voiceover as the creator speaking.

Rules:

1. Translate facts, do not invent. Do not add claims, dates, prices or names that are not in the original clip or hook. Machine translation can slip: read each language's captions and hook before the human posts, and fix wrong or odd lines (ask the human if a language is unfamiliar).
2. Run `rule-check` on each language version, same as the original.
3. Post localized versions on separate localized pages or accounts, or as multi-language uploads where the platform supports them (for example YouTube multiple audio tracks and translated titles). Do not spam the same page with five versions of one clip.
4. Captions: X no hashtags; Instagram 3 to 5 hashtags; TikTok and Shorts short plus a few hashtags.
5. Do not upload anything. Show the files and captions to the user.
