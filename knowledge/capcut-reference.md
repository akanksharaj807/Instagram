# CapCut iPad/Mobile — Complete UI Reference

> This file is the source of truth for all CapCut instructions in this project.
> Every `reel-capcut` output must use the tap paths defined here.
> User edits on iPad. All instructions must be micro-level: exact panel names, exact button names, exact sequences of taps.

---

## UI Layout (know this before writing any instruction)

```
┌─────────────────────────────────┐
│         PREVIEW WINDOW          │  ← see your edit live here
├─────────────────────────────────┤
│         TIMELINE                │  ← clips laid out left to right
│  [clip1]─|─[clip2]─|─[clip3]   │  ← | = transition point
├─────────────────────────────────┤
│   BOTTOM TOOLBAR (scrollable)   │  ← changes based on what's selected
└─────────────────────────────────┘
```

- **Top right corner** → Export button (↑ arrow icon)
- **Top left** → Back arrow
- **Playhead** → white vertical line in timeline; drag it to scrub
- **Timeline zoom** → pinch in/out to zoom timeline for precision
- **Clip selected** = white border + handles appear around it; bottom toolbar changes to clip-specific options
- **Nothing selected** = bottom toolbar shows main project options

---

## 1. Starting a Project

```
Open CapCut
→ Tap "New project"
→ Tap videos from your Camera Roll to select them (checkmark appears)
→ Tap "Add" (bottom right)
→ Project opens in editor
```

**To add more clips later:**
```
Tap the "+" at the end of the timeline
→ Select clip(s)
→ Tap "Add"
```

---

## 2. Trimming (shorten a clip from either end)

```
Tap the clip in the timeline  [clip gets white border + handles]
→ Press and hold the LEFT white handle → drag RIGHT to trim the start
→ Press and hold the RIGHT white handle → drag LEFT to trim the end
→ Tap anywhere outside the clip to deselect
```

**Precision tip:** Pinch the timeline to zoom in first — handles become easier to grab.

**Watch the timecode:** as you drag, a timecode display shows the exact time — use it to hit precise in/out points.

---

## 3. Splitting (cut a clip into two pieces)

```
Drag the timeline so the playhead (white line) lands exactly where you want the cut
→ Tap the clip to select it
→ Tap "Split" in the bottom toolbar
→ Clip becomes two separate clips at that point
```

**To cut out a middle section:**
```
Split at the START of the section → then split at the END of the section
→ Select the middle piece → tap "Delete"
```

---

## 4. Deleting a Clip

```
Tap the clip to select it
→ Tap "Delete" in the bottom toolbar
→ Clip is removed; remaining clips close the gap automatically
```

---

## 5. Rearranging Clips

```
Long press the clip in the timeline (hold ~1 second until it lifts)
→ Drag left or right to new position
→ Release to drop it there
```

---

## 6. Transitions (between clips)

The **|** icon between two clips is the transition point.

```
Tap the "|" icon between two clips
→ Transition panel opens at bottom
→ Browse categories: Basic | Cinematic | Blur | Dissolve | Glitch | etc.
→ Tap any transition to preview it
→ Adjust DURATION using the slider at the bottom (0.1s – 2.0s)
→ Tap ✓ to confirm
```

**To remove a transition:**
```
Tap the "|" icon → tap "None" (first option)
```

**For no-cut / seamless feel:** use "Dissolve" at 0.3–0.5s
**For fast, punchy edits:** use "Basic > Swipe" or no transition at 0s

---

## 7. Aspect Ratio / Format (set this FIRST, before anything else)

For Reels / TikTok: 9:16
For YouTube: 16:9

```
Tap "Format" in the main bottom toolbar (scroll left/right to find it)
→ Tap the ratio you want: 9:16 / 16:9 / 1:1 etc.
→ If clips don't fill the frame:
     Tap "Canvas" → choose "Blur" (blurred version of clip fills background)
     OR choose "Color" and pick a background color
→ To manually resize a clip to fill: select clip → pinch to scale in preview window
```

---

## 8. Text (title cards, captions, callouts)

### Add a text element
```
Tap "Text" in the main bottom toolbar
→ Tap "Add text"
→ Type your text → tap "Done" on keyboard
→ Text box appears in preview — drag it to position
→ Pinch to resize the text box
```

### Style the text
With text selected:
```
Bottom tabs: Text | Font | Style | Effects | Animation | Align
→ "Text" tab: change the words
→ "Font" tab: choose font (scroll to browse)
→ "Style" tab: color, stroke (outline), shadow, background box
→ "Effects" tab: glitch, neon, 3D, etc.
→ "Animation" tab: how text enters/exits (Fade in, Typewriter, etc.)
→ "Align" tab: left / center / right alignment
```

### Control WHEN text appears (duration)
```
After adding text, look in the timeline — a colored text bar appears below the clips
→ Drag its LEFT handle to set when text starts
→ Drag its RIGHT handle to set when text ends
→ It only shows during that window
```

### Common text instruction format to give user:
> Tap Text → Add text → type "[TEXT]" → Font tab: pick [FONT] → Style tab: color [COLOR], add stroke [COLOR] → drag to [POSITION] in preview → set duration [START]s to [END]s in timeline

---

## 9. Auto Captions (spoken word → subtitles automatically)

```
Tap "Text" in main toolbar
→ Tap "Auto captions"
→ Select language (English)
→ Tap "Start"
→ Wait — CapCut transcribes the audio
→ Captions appear in timeline as individual blocks
→ Tap any caption block to edit the text if it got a word wrong
→ Select all caption blocks → tap "Style" to style all at once (font, color, size)
```

---

## 10. Stickers / Overlays

```
Tap "Stickers" in main toolbar
→ Search bar at top or browse categories
→ Tap a sticker to add it
→ Drag to position in preview
→ Pinch to resize
→ In timeline, drag sticker bar to set when it appears and for how long
```

---

## 11. Audio — Background Music

```
Tap "Audio" in main toolbar
→ Tap "Music"
→ Browse CapCut's library (by mood/genre) OR tap "My music" for tracks on your device
→ Tap a track to preview
→ Tap "+" or "Use" to add it to timeline
→ Audio bar appears below clips in timeline
→ Trim it: tap audio bar → drag handles to trim
→ Volume: tap audio bar → tap "Volume" → drag slider
→ Fade: tap audio bar → tap "Fade" → set Fade In / Fade Out duration
```

---

## 12. Audio — Voiceover (record your own voice)

```
Tap "Audio" in main toolbar
→ Tap "Voiceover"
→ Move playhead to where you want to start
→ Press and HOLD the red record button to record
→ Release to stop
→ Recording appears as audio bar in timeline
→ Trim/adjust same as music
```

---

## 13. Audio — Extract Audio from Another Video

```
Tap "Audio" in main toolbar
→ Tap "Extracted"
→ Select a video from your Camera Roll
→ Tap "Only import audio"
→ Audio strip appears in timeline
```

---

## 14. Volume Control

For any audio bar (music, voiceover, original clip audio):
```
Tap the audio bar in timeline to select it
→ Tap "Volume" in bottom toolbar
→ Drag slider: 0 = silent, 100 = original, 200 = double
```

**To mute original clip audio:**
```
Tap the video clip → tap "Volume" → drag to 0
```

---

## 15. Filters (color mood — applies a preset look)

**To apply to ONE clip:**
```
Tap the clip in timeline to select it
→ Scroll bottom toolbar → tap "Filter"
→ Browse: Natural | Portrait | Film | Food | Vintage | etc.
→ Tap filter to preview
→ Drag the intensity slider
→ Tap ✓
```

**To apply to ALL clips (whole video):**
```
Tap anywhere on timeline so nothing is selected
→ Tap "Filters" in main toolbar
→ Same as above — applies to whole project
```

---

## 16. Color Adjustment (manual — brightness, contrast, etc.)

```
Tap the clip in timeline to select it
→ Scroll bottom toolbar → tap "Adjust"
→ Controls appear (tap each, then drag the slider):
   Brightness   → how light/dark the image is
   Contrast     → difference between light and dark areas
   Saturation   → how vivid the colors are (0 = black & white)
   Sharpen      → crisp up soft footage
   Highlights   → recover blown-out bright areas (drag left)
   Shadows      → lift dark areas (drag right to show detail)
   Temperature  → warm (right, orange) or cool (left, blue)
   Vignette     → dark edges drawing eye to center
→ Tap ✓ to confirm
```

---

## 17. Speed Adjustment

```
Tap the clip in timeline to select it
→ Tap "Speed" in bottom toolbar
→ Two options:
```

**Normal speed** (simple):
```
→ Tap "Normal"
→ Drag slider: 0.1x (very slow) to 100x (very fast)
→ Tap ✓
```

**Curve speed** (advanced — speed changes within the clip):
```
→ Tap "Curve"
→ Pick a preset: Montage / Hero / Bullet / Jump Cut / Flash In / Flash Out
   OR tap "Custom" to draw your own curve
→ Drag the dots on the curve to control speed at each point
   (higher dot = faster, lower dot = slower)
→ Tap ✓
```

---

## 18. Video Effects (visual effects on the clip)

```
Tap "Effects" in main toolbar
→ Two tabs: Video effects | Body effects
→ Tap "Video effects"
→ Browse: Basic | Retro | Distort | Cinema | Nature | etc.
→ Tap an effect to preview (it applies at current playhead)
→ In timeline, drag the effect bar to set duration
→ Tap the effect bar → "Adjust" to change intensity
```

---

## 19. Animation (how a clip enters or exits)

```
Tap the clip in timeline to select it
→ Scroll bottom toolbar → tap "Animation"
→ Three tabs: In | Out | Combo
   "In" = animation when clip starts (Fade in, Zoom in, Slide in, etc.)
   "Out" = animation when clip ends (Fade out, etc.)
   "Combo" = loops throughout the clip
→ Tap your choice → drag the duration slider
→ Tap ✓
```

---

## 20. Keyframe (animate position/scale/opacity over time)

Use this to make a zoom, pan, or fade happen within a single clip.

```
Tap the clip to select it
→ Move playhead to the START point of the animation
→ Tap the ◆ (diamond) icon that appears above the timeline
   → first keyframe is set
→ Move playhead to the END point
→ In preview window: pinch to scale the clip / drag to reposition
   → second keyframe is set automatically
→ CapCut animates between the two
```

---

## 21. Remove Background (AI background removal)

```
Tap the clip in timeline to select it
→ Scroll bottom toolbar → tap "Remove BG"
→ Two options:
   "Auto removal" → AI removes background automatically
   "Custom removal" → you paint/select what to remove
→ Wait for processing
→ Tap ✓
```

---

## 22. Blur / Mosaic (to hide a logo or watermark)

CapCut doesn't have a direct delogo tool. Use this workaround:

```
Tap "Stickers" in main toolbar
→ Search "blur" OR browse for a blur/mosaic overlay sticker
→ Add it → drag and resize over the watermark in preview
→ Set duration in timeline to cover the full clip
```

OR use a shape:
```
Tap "Stickers" → tap the shape icon → pick a solid rectangle
→ Set color to match background → place over the watermark
```

---

## 23. Overlay (picture-in-picture, second video on top)

```
Tap "Overlay" in main toolbar (some versions: scroll to find it)
→ Tap "Add overlay"
→ Select a clip or image from Camera Roll
→ It appears as a separate layer above the main clip in timeline
→ In preview: drag to position, pinch to resize
→ Trim its duration handles in timeline
→ Tap "Mix" to control how it blends with the layer below (opacity, blend mode)
```

---

## 24. Green Screen (Chroma Key)

```
Add the clip as an Overlay (step above)
→ With the overlay selected, scroll bottom toolbar → tap "Chroma key"
→ Use the eyedropper to tap the green color in preview
→ Adjust Intensity and Shadow sliders
→ Tap ✓
```

---

## 25. Export

Always set ratio and review full video before exporting.

```
Tap the ↑ (export) button — top right corner
→ Select Resolution: 1080p (recommended for Reels)
→ Select Frame Rate: 30fps (standard) or 60fps (smoother motion)
→ Tap "Export"
→ Wait for rendering (progress bar)
→ Video saves to Camera Roll automatically
→ Tap the share icon to post directly to Instagram / TikTok
```

---

## Quick Reference — Bottom Toolbar Cheat Sheet

| What you want to do | How to get there |
|---|---|
| Trim a clip | Tap clip → drag white handles |
| Split / cut | Move playhead → tap clip → "Split" |
| Delete | Tap clip → "Delete" |
| Transition | Tap "\|" between clips |
| Change ratio | Main toolbar → "Format" |
| Add text | Main toolbar → "Text" → "Add text" |
| Auto captions | Main toolbar → "Text" → "Auto captions" |
| Add music | Main toolbar → "Audio" → "Music" |
| Record voice | Main toolbar → "Audio" → "Voiceover" |
| Mute clip audio | Tap clip → "Volume" → 0 |
| Add filter | Tap clip → "Filter" OR main toolbar → "Filters" |
| Adjust color | Tap clip → "Adjust" |
| Change speed | Tap clip → "Speed" |
| Add sticker | Main toolbar → "Stickers" |
| Add overlay | Main toolbar → "Overlay" → "Add overlay" |
| Video effects | Main toolbar → "Effects" → "Video effects" |
| Animate clip | Tap clip → "Animation" |
| Keyframe | Tap clip → tap ◆ icon |
| Remove BG | Tap clip → "Remove BG" |
| Export | Top right ↑ button |

---

## Instruction Format Rules (for reel-capcut skill output)

When writing CapCut steps for a specific video, always follow this pattern:

1. **Action header** — what this step achieves (e.g., "Trim the opening clip to 3 seconds")
2. **Exact tap path** — written as `Tap X → tap Y → drag Z`
3. **Target value** — the specific setting, duration, color, or position
4. **Why** — one sentence on why this edit matters for this reel (retention, hook, etc.)

Never write vague instructions like "add a filter." Always write:
> Tap the clip → tap "Filter" → tap "Film" category → tap "Kodak" → drag intensity to 70 → tap ✓
