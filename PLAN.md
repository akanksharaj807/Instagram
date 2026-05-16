# Reels Agent — Master Plan

> Read this at the start of every session alongside README.md.

---

## What this system does

The user drops a reference video (a reel they want to recreate). Claude analyzes every frame of it, plans how to recreate it with the user's content, tells the user how to shoot, and then writes a step-by-step CapCut edit guide. The user films and edits manually. Claude never touches the edit.

**The goal every single time: recreate the reference reel.**

---

## How to read videos — critical

Claude cannot watch video files. It reads images. Every video must be sliced into frames first using ffmpeg.

### The ffmpeg binary

Installed via pip (no brew needed):

```bash
FF=$(python3 -c "import imageio_ffmpeg; print(imageio_ffmpeg.get_ffmpeg_exe())")
```

If missing: `pip3 install --user imageio-ffmpeg`

### Rules

1. Videos must be inside `/Users/akanksharaj/Desktop/I/` before slicing.
2. macOS screen recordings have a narrow no-break space (U+202F) before AM/PM in the filename. Use a wildcard: `Screen\ Recording*2026-05-16*.mov`
3. ffmpeg reads picture only — no audio. Spoken hooks and music must be typed by the user.

### Standard slice command

```bash
FF=$(python3 -c "import imageio_ffmpeg; print(imageio_ffmpeg.get_ffmpeg_exe())")
"$FF" -i "[VIDEO_PATH]" -vf "fps=4,scale=720:-1" -q:v 4 \
  "/Users/akanksharaj/Desktop/I/frames/ref_%04d.jpg" \
  -hide_banner -loglevel error
```

Probe first: `"$FF" -i "[VIDEO_PATH]" 2>&1 | grep -E "Duration|Video"`

### fps guide

| Content type | fps | Frame interval |
|---|---|---|
| Fast-cut / trend reels (default) | fps=4 | 1 frame every 0.25s |
| Very aggressive — 1+ cuts per second | fps=6 | 1 frame every 0.17s |
| Slow / cinematic / talking-head | fps=2 | 1 frame every 0.5s |
| Long-form 60s+ | fps=1 | 1 frame per second |

Timestamp formula: frame N × (1 ÷ fps) = seconds into video.

---

## The pipeline

```
/reel-reference  → analyze the reference video frame by frame
/reel-blueprint  → plan the recreation with the user's content
/reel-capcut     → write shoot guide + CapCut edit checklist
/reel-ugc        → UGC layer (only when user asks)
/reel-review     → review the finished cut
```

No setup step. User drops the reference video in Desktop/I and runs `/reel-reference`.

---

## File structure

```
/Users/akanksharaj/Desktop/I/
├── PLAN.md
├── README.md
├── CLAUDE.md
├── knowledge/
│   ├── viral-principles.md
│   ├── hook-library.md
│   ├── text-design-system.md
│   ├── retention-playbook.md
│   ├── capcut-reference.md
│   └── ugc-playbook.md
├── skills/
│   ├── reel-reference/skill.md
│   ├── reel-blueprint/skill.md
│   ├── reel-capcut/skill.md
│   ├── reel-ugc/skill.md
│   └── reel-review/skill.md
├── frames/           ← temporary, deleted after every analysis
└── [video-name]/     ← created by reel-capcut when writing output
    ├── guide.md      ← shoot guide + caption
    └── edit-guide.html ← interactive CapCut checklist
```

---

## Status

- [x] Pipeline built and tested
- [x] ffmpeg via imageio-ffmpeg (no brew)
- [x] All 6 knowledge files populated
- [x] All 5 skill files written
- [x] HTML interactive CapCut checklist format defined
- [ ] First real video run end-to-end
