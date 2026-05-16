# CLAUDE.md — Reels Agent

This file is auto-loaded by Claude Code at the start of every session.

## Read these two files first, every session, before doing anything else

1. `PLAN.md` — system setup, ffmpeg binary, file structure, sandbox rules
2. `README.md` — how Claude analyzes, decides, and outputs for every video

Do not respond to the user until both are read.

## How this system works — always in this order

**Step 1 — User gives the reference video.**
Claude analyzes every frame: camera angles, lighting, shot distances, hook placement, cut rhythm, text style, everything.

**Step 2 — Claude tells the user how to shoot.**
Based on the reference analysis, Claude writes a filming guide: what angle to hold the phone, what light to turn on/off, how close to stand, what to do in each shot, where the hook lands, how long to film each clip.

**Step 3 — User goes and films.**

**Step 4 — User gives Claude the raw footage.**
Claude looks at what was filmed and compares it against the reference.

**Step 5 — Claude writes the CapCut edit guide.**
Step by step, every tap, referencing both the raw footage and the reference — so the final edit matches the reference's DNA.

Claude never edits automatically. Claude never skips to Step 5 without Steps 1–4. The user films and edits manually.

## Non-negotiable rules (memorize these)

1. **CapCut is the only editing surface.** No Volcengine API. No automated edits. Ever.
2. **Every CapCut tap path comes from `knowledge/capcut-reference.md`.** Never invent UI steps.
3. **UGC angle comes from the reference analysis in conversation context only.** Never use Claude's default UGC training patterns. Never.
4. **reel-ugc runs only when the user explicitly asks for it.**
5. **Every blueprint decision must be traceable to a knowledge file.** No design choices from thin air.
6. **The DM share test is mandatory for every blueprint.** "Who specifically sends this to whom and why?"
7. **Counter-trend check before any editing decision.** Does the reference use raw/authentic format? If yes, do not add hyper-editing techniques it doesn't use.
8. **Do not optimize for likes.** Weakest signal. Irrelevant.

## Pipeline (run in order)

```
/reel-reference  → skills/reel-reference/skill.md → analysis stays in conversation (no file)
/reel-blueprint  → skills/reel-blueprint/skill.md → recreation plan stays in conversation (no file)
/reel-capcut     → skills/reel-capcut/skill.md    → writes guide.md (shoot guide + caption) + edit-guide.html (CapCut checklist)
/reel-ugc        → skills/reel-ugc/skill.md       → appends to guide.md (only when asked)
/reel-review     → skills/reel-review/skill.md    → review in conversation (no file)
```

**No setup needed.** Drop the reference video anywhere inside `Desktop/I` and run `/reel-reference`.

**Two output files:** `guide.md` (shoot guide + caption) and `edit-guide.html` (interactive CapCut checklist the user opens on their phone while editing).

## Knowledge base (what each stage reads)

| File | Read in |
|---|---|
| `knowledge/viral-principles.md` | reel-blueprint, reel-review |
| `knowledge/retention-playbook.md` | reel-blueprint, reel-reference, reel-capcut |
| `knowledge/hook-library.md` | reel-blueprint, reel-reference |
| `knowledge/text-design-system.md` | reel-blueprint, reel-capcut |
| `knowledge/capcut-reference.md` | reel-capcut (always), reel-review |
| `knowledge/ugc-playbook.md` | reel-ugc only |

## ffmpeg (required for reading any video)

```bash
FF=$(python3 -c "import imageio_ffmpeg; print(imageio_ffmpeg.get_ffmpeg_exe())")
```

Videos must be inside `/Users/akanksharaj/Desktop/I/` before slicing.
macOS screen recordings: use wildcards — filename has a narrow no-break space before AM/PM.

## Signal hierarchy (north star for every decision)

1. DM Shares — highest weight
2. Watch Time / Retention
3. Saves
4. Comments
5. Likes — ignore
