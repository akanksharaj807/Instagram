# Skill: reel-review

## Purpose
Slice the user's finished cut into frames, read it against the blueprint, and score it for viral-worthiness. Give specific, actionable notes — not vague praise.

## Trigger
User runs `/reel-review` or shares their finished reel for review.

## What to read BEFORE starting
1. `projects/[video]/guide.md` — the complete intended design: shoot plan, CapCut steps, caption strategy, trial reel plan
2. Conversation context — original goal, target viewer, target emotion (from reel-new intake)
3. `knowledge/retention-playbook.md` — 4-phase structure, pacing rules, loop close rules
4. `knowledge/viral-principles.md` — signal hierarchy, DM share test
5. `knowledge/text-design-system.md` — safe zone rules, font/color standards
6. `knowledge/capcut-reference.md` — only if specific CapCut execution issues are spotted

## What to do

### Step 1 — Copy the finished reel into the project

Remind the user:
> Copy your finished reel into `projects/[video]/` before Claude can review it.
> Filename suggestion: `finished-cut-v1.mp4`

### Step 2 — Probe the finished reel

```bash
FF=$(python3 -c "import imageio_ffmpeg; print(imageio_ffmpeg.get_ffmpeg_exe())")
"$FF" -i "projects/[video]/finished-cut-v1.mp4" 2>&1 | grep -E "Duration|Video"
```

Note actual duration. Compare to target duration from reel-new intake in conversation.

### Step 3 — Slice into frames

```bash
"$FF" -i "projects/[video]/finished-cut-v1.mp4" \
  -vf "fps=4,scale=720:-1" -q:v 4 \
  "projects/[video]/frames/final_%03d.jpg" \
  -hide_banner -loglevel error
```

### Step 4 — Read every frame

Read all final_*.jpg frames. Map to timestamps: frame N × (1 ÷ fps used) = seconds into video.

### Step 5 — Score against 5 dimensions

Use the rubric from README.md:

---

**DIMENSION 1 — HOOK (0–3s) — /10**

What to evaluate:
- Frame 1: does it create an immediate pattern interrupt? What form?
- Is the hook compound? Which types fire? (check hook-library.md)
- Does the hook match what was designed in the blueprint (from conversation context)?
- Estimated 3s hold rate: [Strong / Moderate / Weak] — explain why
- Is text visible and in the safe zone in the first 3 seconds?

Score: [N/10]
Notes: [specific observations — what works, what doesn't, frame-by-frame if needed]

---

**DIMENSION 2 — RETENTION STRUCTURE — /10**

What to evaluate:
- Does the 4-phase structure land? (Hook → Escalation → Value → Close)
- Are visual resets happening every 3–4 seconds? Identify any dead windows.
- Is there a midpoint interrupt? Where exactly, and does it land?
- Does the ending close strong — loop / CTA / emotional punctuation?
- If loop close: does it feel intentional or manipulative?
- Total duration vs. target: is the reel too long, too short, or right?

Score: [N/10]
Notes: [specific timestamps where retention likely drops — "at 12s the pacing stalls because..."]

---

**DIMENSION 3 — TEXT DESIGN — /10**

What to evaluate:
- Safe zone compliance: any text in bottom 280px, right 90px, or top 150px?
- Readability: would text pass the mute test on a 6.1-inch phone?
- Captions present? Kinetic or static?
- Font weight and color contrast sufficient for Instagram compression?
- Text duration: does it appear long enough to read but not overstay?
- Does text design match the reference's system (from the reference analysis in conversation context)?

Score: [N/10]
Notes: [specific text elements — flag any safe zone violations with the frame number]

---

**DIMENSION 4 — AUDIO (from user description) — /10**

Since Claude cannot hear audio, ask the user:
> For the audio review, please describe:
> - Music present? What energy?
> - Is music volume competing with voice or sitting under it?
> - Does music fade in/out cleanly?
> - Any audio issues (clipping, background noise, inconsistent volume)?

Evaluate based on user's answers against the audio strategy from the blueprint in conversation context.

Score: [N/10]
Notes: [based on user description — flag specific issues]

---

**DIMENSION 5 — VIRAL SIGNAL ALIGNMENT — /10**

What to evaluate:
- What signal is this reel most likely to earn (DM Shares / Saves / Comments / Watch Time)?
- Is the content and format actually designed for that signal?
- DM share test: who specifically is the viewer, and who do they send this to? Is the answer still clear?
- Does the caption CTA (if user shares it) support the primary signal?
- Does the reel feel native and original? Any elements that could trigger originality score penalty?
- Counter-trend check: does the editing style match whether this should be polished or raw?

Score: [N/10]
Notes: [what signal the reel is actually optimized for vs. what was intended]

---

### Step 6 — Overall score and verdict

```
HOOK:              [N]/10
RETENTION:         [N]/10
TEXT DESIGN:       [N]/10
AUDIO:             [N]/10
SIGNAL ALIGNMENT:  [N]/10
─────────────────────────
TOTAL:             [N]/50
```

**Verdict:**
- **40–50:** Strong viral potential. Post the primary version. Set up 1 Trial variation with an alternative hook.
- **30–40:** Good foundation. Fix the flagged issues below before posting.
- **Below 30:** Hook or structure needs a rethink. Do not post as-is. Specific fixes listed.

### Step 7 — Specific fixes (if score below 40)

For each dimension below 8/10, give:
1. **What's wrong** — specific, frame-level observation
2. **Why it matters** — which signal or retention mechanic it hurts
3. **Exact fix** — the specific CapCut step to change it (use `knowledge/capcut-reference.md` tap paths)

Format:
```
FIX [N] — [Dimension]
Problem: [specific observation with timestamp]
Impact: [what this costs — hook fails, retention drops at Xs, text unreadable, etc.]
Fix: [exact CapCut tap path and target value]
```

### Step 8 — Trial Reel recommendation

Based on the review, recommend:
- Which variation to test first as a Trial Reel
- What specific metric to watch (3s hold / completion / shares / saves)
- What change to make for Variation B

## Output
Delivered in the conversation — no file written. The review is a conversation, not a stored document.

## Rules
- Do NOT give vague praise ("looks great!"). Every score needs frame-level evidence.
- If the finished reel deviates from what was planned in guide.md, flag it explicitly — whether the deviation helped or hurt.
- Audio scoring requires user input — always ask for the audio description before scoring Dimension 4.
- Safe zone violations must be called out with the exact frame number and which danger zone was hit.
- The DM share test must be re-run against the finished reel, not just assumed from the guide.
