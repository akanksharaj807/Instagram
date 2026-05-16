# Skill: reel-capcut

## Purpose
Translate the reference analysis and blueprint (from conversation context) into one complete guide the user can follow on their phone: how to film every shot, then how to edit every step in CapCut.

One file. Two parts. Nothing else written.

## Trigger
User runs `/reel-capcut` or asks for the editing guide.

## What to read before writing anything

1. Conversation context — the full reference analysis from `/reel-reference` (especially the Reference DNA Summary)
2. Conversation context — all blueprint decisions from `/reel-blueprint` (hook, structure, text, audio, color, caption)
3. Conversation context — clip labels, durations, constraints (from reel-new intake)
4. `knowledge/capcut-reference.md` — **ALWAYS read this** — all CapCut tap paths live here; never invent UI steps
5. `knowledge/text-design-system.md` — fonts, colors, sizes, safe zones
6. `knowledge/retention-playbook.md` — retention tactics to weave into the edit

## Output
This skill creates TWO files:
1. `projects/<video>/guide.md` — shooting guide (Part 1) + caption/hashtags/trial reel strategy
2. `projects/<video>/edit-guide.html` — the CapCut edit steps as an interactive HTML checklist the user opens on their phone while editing in CapCut

---

## How to write guide.md

### Part 1: How to Film Your Shots

Derived entirely from the Reference DNA Summary in conversation. Translate what the reference does visually into specific filming instructions for the user's content.

**Rules for Part 1:**
- Write for someone who has never filmed a reel before
- Every instruction must be physical and specific — not "look natural", but "hold the product at chest height, slightly angled, arm relaxed"
- Lighting instructions must name exactly what to turn on and what to turn off
- Camera movement must have a speed (e.g. "pan over 3–4 seconds, slow enough that it feels too slow")
- Each shot gets a duration range to guide how much footage to capture
- End with ONE practical tip that unlocks the reference's single most defining visual quality

**Structure:**

```
## Part 1: How to Film Your Shots

**Setup**
- [What lights to turn on/off, where to position them]
- [What to have in the background / what to clear]
- [What to wear or hold or place in frame]
- [Phone position / tripod / propped — whatever the reference implies]

**Shot [N] — [Descriptive name]**
Film: [X–Y seconds of footage]
Camera: [position, distance, movement]
Light: [which light source, where relative to subject]
What to do: [exact physical instruction — what to move, say, reveal, or hold]

[... each shot ...]

**[The one visual trick that does the most work]:**
[One practical paragraph. The single insight from the reference's visual signature that makes the whole thing look right. Lighting, framing, or movement — whichever is the heaviest lever for this specific reference.]
```

---

### Part 2: edit-guide.html (interactive CapCut checklist)

This is a **separate HTML file** the user opens on their phone browser while editing in CapCut. They tap each step to check it off as they go. It has a live progress bar.

**Rules:**
- Every tap path comes from `knowledge/capcut-reference.md` — never invent UI steps
- Name every clip by its label from the reel-new intake in conversation — never "the first clip"
- Every step title gets ONE tag: `tap` (blue — user taps something), `set` (yellow — user sets a value), or `must` (red — critical, do not skip)
- The step detail gives the exact instruction + one sentence why. Specific numbers always: hex colors, seconds, percentages, speed multipliers
- Steps are micro. One action per step. Never combine two actions into one step.
- Phases group related steps. Phase names are short and lowercase.

**Tags to use:**
- `tap` — any navigation, selection, or button press
- `set` — any value being entered: brightness, volume, speed, duration, color
- `must` — a step that will break the edit if skipped (aspect ratio first, 4K setting, curve not basic, etc.)

**HTML template to output:**

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>[VIDEO NAME] — CapCut Edit</title>
<style>
  *{box-sizing:border-box;margin:0;padding:0}
  body{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;background:#0f0f0f;color:#e5e5e5;padding:1rem;max-width:480px;margin:0 auto}
  h1{font-size:16px;font-weight:600;color:#fff;margin-bottom:1.5rem;padding-bottom:0.75rem;border-bottom:1px solid #2a2a2a}
  .progress-label{font-size:12px;color:#888;margin-bottom:6px}
  .progress-bar{height:3px;background:#2a2a2a;border-radius:2px;margin-bottom:1.5rem;overflow:hidden}
  .progress-fill{height:100%;background:#1D9E75;border-radius:2px;transition:width 0.3s}
  .phase{margin-bottom:1.5rem}
  .phase-label{font-size:10px;font-weight:600;text-transform:uppercase;letter-spacing:0.1em;color:#555;margin-bottom:8px;padding-left:4px}
  .step{display:flex;align-items:flex-start;gap:10px;padding:10px 12px;border-radius:10px;cursor:pointer;border:0.5px solid transparent;transition:background 0.15s;margin-bottom:4px}
  .step:hover{background:#1a1a1a}
  .step.done{background:#1a1a1a}
  .step-num{width:24px;height:24px;border-radius:50%;border:0.5px solid #333;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:500;color:#666;flex-shrink:0;margin-top:1px;transition:all 0.15s}
  .step.done .step-num{background:#1D9E75;border-color:#1D9E75;color:#fff}
  .step-done-icon{display:none;font-size:13px}
  .step.done .step-done-icon{display:block}
  .step.done .step-num-text{display:none}
  .step-body{flex:1}
  .step-title{font-size:14px;font-weight:500;color:#e5e5e5;margin:0 0 3px}
  .step.done .step-title{color:#555;text-decoration:line-through}
  .step-detail{font-size:12px;color:#888;line-height:1.5}
  .step.done .step-detail{color:#444}
  .step-tag{display:inline-block;font-size:10px;padding:2px 7px;border-radius:20px;margin-left:6px;font-weight:600;vertical-align:middle}
  .tag-tap{background:#1a3a5c;color:#60a5fa}
  .tag-set{background:#3a2a00;color:#fbbf24}
  .tag-must{background:#3a1a1a;color:#f87171}
  .divider{height:1px;background:#1e1e1e;margin:1.5rem 0}
  .reset-btn{font-size:12px;color:#555;background:none;border:1px solid #2a2a2a;border-radius:6px;cursor:pointer;padding:8px 14px;margin-top:1rem;width:100%}
</style>
</head>
<body>
<h1>[VIDEO NAME] — CapCut Edit Guide</h1>

<div class="progress-label" id="prog-label">0 of [TOTAL] steps done</div>
<div class="progress-bar"><div class="progress-fill" id="prog-fill" style="width:0%"></div></div>

<!-- PHASE 1 -->
<div class="phase">
  <div class="phase-label">Phase 1 — [phase name]</div>

  <div class="step" onclick="toggle(this)">
    <div class="step-num"><span class="step-num-text">1</span><span class="step-done-icon">✓</span></div>
    <div class="step-body">
      <p class="step-title">[Step title] <span class="step-tag tag-must">must</span></p>
      <p class="step-detail">[Exact instruction. Specific values. One sentence why.]</p>
    </div>
  </div>

  <div class="step" onclick="toggle(this)">
    <div class="step-num"><span class="step-num-text">2</span><span class="step-done-icon">✓</span></div>
    <div class="step-body">
      <p class="step-title">[Step title] <span class="step-tag tag-tap">tap</span></p>
      <p class="step-detail">[Exact instruction.]</p>
    </div>
  </div>

</div>

<div class="divider"></div>

<!-- PHASE 2 — repeat pattern for every phase -->

<button class="reset-btn" onclick="resetAll()">Reset all steps</button>

<script>
  const total = [TOTAL];
  function toggle(el){el.classList.toggle('done');updateProgress()}
  function updateProgress(){
    const done=document.querySelectorAll('.step.done').length;
    document.getElementById('prog-fill').style.width=Math.round(done/total*100)+'%';
    document.getElementById('prog-label').textContent=done+' of '+total+' steps done';
  }
  function resetAll(){document.querySelectorAll('.step.done').forEach(s=>s.classList.remove('done'));updateProgress()}
</script>
</body>
</html>
```

**Phase order for the HTML:**
- Phase 1: before you film (any camera settings the user needs to set before shooting)
- Phase 2: import & arrange
- Phase 3: rough cut (trims, clip order)
- Phase 4: speed ramp (if reference uses one)
- Phase 5: transitions
- Phase 6: text & captions
- Phase 7: audio
- Phase 8: colour & filters
- Phase 9: effects & animations
- Phase 10: export

Only include phases that the blueprint actually calls for. Skip phases that aren't needed for this specific reel.

---

### Before You Post (at the end of guide.md)

Include the caption, hashtags, and alt text from the blueprint — everything the user needs before hitting publish.

```
## Before You Post

**Caption**
[Line 1 — the hook that triggers "...more"]

[Body — natural language, keywords, value]

[CTA — polarizing question / automation keyword / confession prompt]

**Hashtags**
#[tag] #[tag] #[tag] #[tag]

**Alt text**
[One keyword-rich sentence describing the visual content]

**Trial Reel strategy**
Post [Variation A] first. Watch [metric] for 24h. If [threshold] → post [Variation B].
```

---

## What gets written where

### guide.md contains:
- Part 1: How to Film Your Shots
- Before You Post (caption, hashtags, alt text, trial reel strategy)

### edit-guide.html contains:
- All CapCut editing steps as the interactive checklist (Phase 1 through export)

**guide.md template:**

```markdown
# [Video Name] — Shoot Guide

## How to Film Your Shots

**Setup**
- [lighting]
- [background / environment]
- [what to wear / hold / place in frame]
- [phone position]

**Shot [N] — [Descriptive name]**
Film: [X–Y seconds of footage]
Camera: [position, distance, movement]
Light: [source and position]
What to do: [exact physical instruction]

[... all shots ...]

**[Visual signature tip headline]:**
[One practical paragraph — the single most important insight from the reference's visual DNA]

---

## Before You Post

**Caption**
[line 1]
[body]
[CTA]

**Hashtags**
#tag #tag #tag #tag

**Alt text**
[text]

**Trial Reel strategy**
[which variation first, which metric to watch, what to test next]

---

*CapCut editing steps → open edit-guide.html on your phone*
```
