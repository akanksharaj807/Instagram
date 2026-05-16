# Skill: reel-reference

## Purpose
Find the reference video, slice it into frames, read every frame forensically, and decode every single edit decision shot-by-shot. This is the foundation. Everything downstream — shoot guide, CapCut steps — comes from what is extracted here.

Analysis stays in the conversation. No file written.

## Trigger
User runs `/reel-reference` or drops a reference video and asks Claude to analyze it.

## What to read BEFORE starting
1. `README.md` — the forensic frame-reading protocol (Stage 2 section)
2. `knowledge/hook-library.md` — to identify which hook types the reference uses
3. `knowledge/retention-playbook.md` — to map the retention structure onto the reference
4. `knowledge/viral-principles.md` — to identify which viral signal the reference targets

## What to do

### Step 1 — Find the reference video

```bash
find /Users/akanksharaj/Desktop/I -name "*.mov" -o -name "*.mp4" | grep -v frames | grep -v ".DS_Store"
```

If multiple videos are found, list them and ask the user which one is the reference. If only one, proceed.

### Step 2 — Get the ffmpeg binary

```bash
FF=$(python3 -c "import imageio_ffmpeg; print(imageio_ffmpeg.get_ffmpeg_exe())")
```

### Step 3 — Probe the video first

```bash
"$FF" -i "[VIDEO_PATH]" 2>&1 | grep -E "Duration|Video"
```

Report duration and resolution to the user before slicing.

### Step 4 — Slice into frames

Pick fps based on edit style. When in doubt use fps=4.

| Content type | fps | Frame interval |
|---|---|---|
| Fast-cut / trend reels (default) | fps=4 | 1 frame every 0.25s |
| Very aggressive — 1+ cuts per second | fps=6 | 1 frame every 0.17s |
| Slow / cinematic / talking-head | fps=2 | 1 frame every 0.5s |
| Long-form 60s+ | fps=1 | 1 frame per second |

```bash
FF=$(python3 -c "import imageio_ffmpeg; print(imageio_ffmpeg.get_ffmpeg_exe())")
mkdir -p /Users/akanksharaj/Desktop/I/frames
"$FF" -i "[VIDEO_PATH]" \
  -vf "fps=4,scale=720:-1" -q:v 4 \
  "/Users/akanksharaj/Desktop/I/frames/ref_%04d.jpg" \
  -hide_banner -loglevel error
```

Timestamp formula: frame N × (1 ÷ fps used) = seconds into video.

### Step 5 — Read every frame

Read all frames using the Read tool. Read in batches if there are many.
Map every frame to its exact timestamp.

### Step 6 — Output the full forensic analysis IN THE CONVERSATION

Not a summary. A forensic map. Shot by shot, second by second. Follow the format from README.md exactly.

The analysis must decode:
- What is the exact compound hook formula this reference uses?
- What is the cut rhythm / pacing signature?
- What visual reset fires every 3–4 seconds?
- Where is the midpoint interrupt and what form does it take?
- What text design system does the reference use — font weight, color, position, animation?
- What POV and shot style — handheld, stabilised, distance, angle?
- Does it use the "after" shot technique?
- What colour grade — warm/cool, crushed shadows, saturation level?
- What emotion does it create and where is the emotional peak?
- What signal is it primarily targeting — DM shares / saves / watch time / comments?
- What makes someone DM this to a specific person?

End with the **Reference DNA Summary** block from README.md. This is what reel-capcut uses to write the shoot guide.

### Step 7 — Delete frames

```bash
rm -rf /Users/akanksharaj/Desktop/I/frames/
```

Confirm: "Frames deleted. Analysis is in the conversation above."

Never keep frames across sessions.

## Output
Full forensic analysis in the conversation. No file written.

## What to tell the user next
> Analysis done. Frames deleted.
> Tell me what your video is about and what you're filming — then run `/reel-blueprint` and I'll plan exactly how to recreate this.
