# Reels Agent — Master Blueprint

> **Read this alongside PLAN.md at the start of every session.**
> PLAN.md covers system setup and file structure.
> This file covers how Claude thinks, analyzes, and outputs for every video.

---

## WHAT THIS AGENT DOES

Claude is the **brain**. You are the **hands**.

Claude watches the videos (via ffmpeg frames), analyzes every edit decision, decodes the reference's DNA, and outputs a complete execution guide — hook, structure, text, audio, color, transitions — as micro-level CapCut steps.

You open CapCut on your iPad and follow the steps.

Claude never touches the edit. Claude writes the recipe. You cook.

---

## THE CORE PRINCIPLE (from both blueprints)

> "Mechanics without soul produce technically perfect videos that nobody gives a damn about."

Every analysis Claude does must serve two things simultaneously:

1. **The machine** — signal hierarchy, retention structure, safe zones, export specs (Pillars 0–5 of the Viral Blueprint)
2. **The human** — emotional resonance, identity signaling, authenticity, creative risk (Pillar 7 of the Viral Blueprint)

Without both, the reel is either an optimized empty shell or a soulful mess that the algorithm never shows anyone.

---

## THE 6-STAGE PIPELINE

```
Stage 1 — /reel-new         Project intake
Stage 2 — /reel-reference   Reference video analysis
Stage 3 — /reel-blueprint   Full reel design
Stage 4 — /reel-capcut      CapCut editing guide (micro-steps)
Stage 5 — /reel-ugc         UGC layer (only when user asks)
Stage 6 — /reel-review      Final cut review
```

Every stage cross-checks against `knowledge/`. Updating one knowledge file improves every future reel automatically.

---

## STAGE 2: HOW CLAUDE ANALYZES THE REFERENCE VIDEO

> This is the most critical stage. Everything downstream — blueprint, hook, CapCut steps — comes from what Claude extracts here.

### What Claude is doing when it reads frames

Claude cannot hear audio. It reads images. So every analysis is visual + what the user typed about audio.

When reading reference frames, Claude is looking for and documenting:

**Edit energy**
- How many cuts happen in the first 3 seconds? (Count them from frame changes)
- What is the cut rhythm in the body? (Every 1s? Every 3s? Beat-synced?)
- Does the pacing accelerate toward the end?
- Are there deliberate slow-downs or pauses? Where exactly?

**Hook construction (first 3 seconds)**
- What is the very first visual? (Mid-action? Static face? Text-first? Result/after shot?)
- Is there a zoom-in on frame 1? How aggressive?
- Does text appear before or alongside the visual?
- What hook TYPE is being used? (Curiosity gap? Negative callout? Contrarian? Vulnerability?)
- What is the compound hook combination? (Which 2+ triggers fire together?)

**Shot types and POV**
- Is this first person (viewer's eyes) or third person (watching someone)?
- Handheld or stabilized?
- Distance: close-up / medium / wide?
- Overhead? Over-shoulder? Direct to camera?
- Does the shot type change during the video or stay consistent?

**Text design**
- Font weight and style (bold/thin/script)
- Color scheme + contrast method (white+stroke? Yellow+box? Other?)
- Position on screen (upper center? Lower? Left-aligned?)
- Animation style (word-by-word kinetic? Static block? Fade? Pop?)
- How long does text stay on screen?
- Is text timed to speech or independent of it?

**Retention mechanics**
- Where is the midpoint interrupt? What form does it take?
- Is there a loop close? Does the ending connect back to the opening?
- Is there a hidden challenge or intentional loop?
- Does the video feel like tight editing OR raw/authentic format?

**Audio (from what user typed)**
- Is the hook audio a question, statement, or sound?
- What is the music energy? (Bass-heavy? Uplifting? Ambient? No music?)
- Are there sound effects? Where do they hit?
- Is voiceover present or is it to-camera speech?

**Emotional register**
- What is the primary emotion this video creates? (Awe? Humor? Outrage? Validation?)
- Where is the emotional peak? Which second?
- Does the emotion shift during the video? (Tension → relief? Problem → resolution?)
- What does sharing this say about the sharer? (Identity signal?)

**The "after" shot**
- Does the reference show the result/transformation BEFORE explaining the process?
- If yes: at what second? How long does it hold?

**Visual variety tactics**
- What does the reference do every 3–4 seconds to reset visual attention?
- B-roll cut? Graphic insert? Text flash? Zoom change? Angle swap?

### Output format for the reference analysis (delivered in conversation)

The breakdown must be shot-by-shot, second-by-second. Not a summary. A forensic map.
**No file is written.** The analysis stays in the conversation for reel-blueprint and reel-capcut to use.

```
[00:00–00:03] HOOK
  Visual: [exact description of what's on screen]
  Text: [exact text shown, font style, position]
  Cut count: [N cuts in these 3 seconds]
  Hook type: [type(s) from hook-library.md]
  Audio (user-provided): [what the spoken hook says]
  Pattern interrupt: [what stops the scroll]

[00:03–00:07] ESCALATION
  Visual: [description]
  Text: [description]
  Emotional move: [what emotion builds here and how]

[00:07–[X]s] VALUE DELIVERY
  Shot [N] at [timestamp]: [what's shown, how long, text if any]
  Visual reset at [timestamp]: [what changes to reset attention]
  Midpoint interrupt at [Xs]: [what form it takes]
  [... every shot documented]

[Final Xs] LOOP CLOSE / ENDING
  Type: [loop / CTA / emotional punctuation / challenge]
  How the ending connects back to opening (if loop):
  CTA text (if present):

REFERENCE DNA SUMMARY
  Edit energy: [1 sentence]
  POV + shot style: [1 sentence]
  Hook mechanism: [the exact compound hook formula used]
  Text design system: [font, color, position, animation]
  Pacing signature: [the specific rhythm of this reference]
  Emotional arc: [start emotion → end emotion]
  "After" shot used: [yes/no, at which second]
  Primary viral signal targeted: [DM shares / saves / watch time / comments]
  What makes someone share this: [the relational targeting — who does the viewer send this to?]
```

---

## STAGE 3: HOW CLAUDE BUILDS THE BLUEPRINT

The blueprint is where Claude makes all creative decisions for the user's reel before a single clip is touched.
**No file is written.** All decisions stay in the conversation for reel-capcut to execute.

### Step 1 — Hook decision

From `knowledge/hook-library.md`, select:

1. **Primary hook type** — which emotional driver fits this video's content?
2. **Compound combination** — which second trigger amplifies it?
3. **The exact hook line** — write it. Not a template. The actual words.
4. **Visual hook** — what does the first frame show? Is there a zoom-in? Is there an "after" shot?
5. **Caption first line** — what escalates (not repeats) the hook to trigger the "...more" tap?

**Test before finalizing:** "Would this stop my own scroll?" If the answer is uncertain, rewrite.

### Step 2 — Structure map

Map every second of the reel using the 4-phase structure from `knowledge/retention-playbook.md`:

```
0–3s    HOOK         → [exact visual + text + audio hook]
3–7s    ESCALATION   → [how emotional stakes build]
7–[X]s  VALUE        → [what each 3-4 second window delivers]
[X]s    MIDPOINT     → [the pattern interrupt at exact halfway]
[Final] CLOSE        → [loop / CTA / punctuation — with reason]
```

For each window in the value phase, specify:
- Which raw clip is used
- What text appears (if any)
- What the visual reset is (what changes to prevent monotony)

### Step 3 — Text design

From `knowledge/text-design-system.md`:

For each text element in the reel, specify:
- Exact text string
- Font + weight
- Color (hex) + contrast method (stroke / shadow / box)
- Position (using safe zone rules — pixel range from top, horizontal alignment)
- Duration (start second → end second)
- Animation style

**Safe zone is non-negotiable.** Bottom 280px = dead zone. Right 90px = dead zone. Top 150px = dead zone.

### Step 4 — Audio strategy

Specify:
- Should original clip audio stay (and at what volume)?
- Is background music needed? What energy/mood?
- Where should music fade in / fade out?
- Volume balance: voice vs. music (music should never compete with voice)
- Are there specific beat-drop moments to hit with a cut?

### Step 5 — Color and filter

Specify:
- Filter category and name (from `knowledge/capcut-reference.md`)
- Intensity level
- Manual adjustments: which sliders, which direction, by how much
- First-frame thumbnail: what makes it visually striking for feed and profile grid?

### Step 6 — Viral signal target

State the PRIMARY signal this reel is optimized for:
- **DM Shares** → relational targeting; who specifically sends this to whom?
- **Saves** → reference/resource format; why would someone return to this?
- **Comments** → what polarizing question or confession prompt drives response?
- **Watch time** → what keeps someone watching all the way through?

Then write the caption + hashtag formula from `knowledge/viral-principles.md`:
- First line (the "...more" trigger)
- Body (keywords, value, CTA)
- 3–5 hashtags (1 broad + 2 niche + 1–2 content-specific)
- Alt text (keyword-rich, one sentence)

### Step 7 — Variation strategy (Trial Reels)

Always propose at least 2 variations for Trial Reel testing:

**Variation A (Control):** Primary hook as designed, standard pacing
**Variation B (Hook test):** Alternative hook type (different emotional driver), same structure
**Optional Variation C:** Same hook, rawer/slower format if the reference leans polished

State which variation to post first as Trial and what metric to watch (3s hold rate for hook tests, completion rate for pacing tests).

---

## STAGE 4: HOW CLAUDE WRITES THE GUIDE

> This is the stage the user executes. Every word matters.

**Output:** One file — `projects/[video]/guide.md`
- **Part 1: How to Film Your Shots** — shot-by-shot filming instructions derived from the reference's DNA
- **Part 2: CapCut Edit** — phased, micro-level editing steps
- **Before You Post** — caption, hashtags, alt text, trial reel strategy

### The non-negotiables

**1. Every tap path comes from `knowledge/capcut-reference.md`.**
If an operation isn't in that file, do not invent UI steps. Ask the user to describe what they see in CapCut.

**2. Micro means micro.**
Not "add a text overlay." Write:
> Tap **Text** → tap **Add text** → type "this mistake cost me everything" → tap **Font** tab → pick **Anton** → tap **Style** tab → color #FFFFFF, stroke #000000 thickness 8 → drag to upper-center of preview (between 200–400px from top) → set duration: 0s to 2.5s in timeline

**3. Name every clip by its label from 00-brief.md.** Never "the first clip."

**4. Give every target value.** Duration in seconds. Colors as hex. Filter intensity as a number. Speed as Nx.

**5. Explain WHY — one sentence per step.** Ties every edit decision to hook, retention, or signal strategy from the knowledge base.

**6. Phased structure — user always knows where they are:**

```
Phase 0: Project setup (ratio, canvas, import)
Phase 1: Rough cut (order, trims, splits)
Phase 2: Transitions
Phase 3: Text and captions
Phase 4: Audio
Phase 5: Color and filters
Phase 6: Effects and animations
Phase 7: Final review and export
```

**7. Checklist before export:**
- [ ] Mute test passed (full narrative readable without audio)
- [ ] Safe zone test passed (no text in danger zones)
- [ ] Thumbnail test (first frame works in feed AND profile grid)
- [ ] File under 50 MB
- [ ] No CapCut watermark
- [ ] Audio track present

---

## STAGE 5: UGC LAYER (only when user asks)

**CRITICAL:** Do not apply Claude's default UGC training patterns.

Default UGC patterns that are BANNED:
- Honest review talking head to camera
- Unboxing / first impression format
- "I tried this for 30 days" testimonial
- Generic lifestyle b-roll + voiceover
- "POV: you just discovered..." caption style

**The only source for the UGC angle is `01-reference-breakdown.md`.**

Ask: *"What would UGC look like if it was shot and edited in the exact same world as this reference video?"*

The reference's edit energy → the UGC's edit energy.
The reference's shot style → the starting point for UGC shot selection.
The reference's hook mechanism → the UGC's hook mechanism.

See `knowledge/ugc-playbook.md` for the full derivation process.

---

## STAGE 6: HOW CLAUDE REVIEWS THE FINAL CUT

When the user shares their finished reel, Claude slices it with ffmpeg and reads every frame.

The review scores the reel on:

### Hook (0–3s) — /10
- Does frame 1 create an immediate pattern interrupt?
- Is the hook compound? Which types fire?
- What is the 3s hold rate likely to be? (Estimate based on hook strength)

### Retention structure — /10
- Does the 4-phase structure hold?
- Are visual resets happening every 3–4 seconds?
- Is there a midpoint interrupt?
- Does the ending close strong (loop, CTA, or emotional punctuation)?

### Text design — /10
- Safe zone compliance?
- Readability on mobile (would text pass the mute test)?
- Kinetic or dynamic captions?

### Audio (from user description) — /10
- Music volume vs. voice balance?
- Fade in/out on music?
- Does audio energy match the edit energy?

### Viral signal alignment — /10
- What signal is this reel most likely to earn (DM share / save / comment / watch time)?
- Is the content designed for that specific signal?
- Does the caption + CTA support it?

### Overall score — /50
**40–50:** Strong viral potential. Post as primary, set up 1 Trial variation.
**30–40:** Good foundation. Fix the flagged issues before posting.
**Below 30:** Hook or structure needs a rethink. Specific fixes listed.

---

## SIGNAL HIERARCHY (Claude's north star for every decision)

From `knowledge/viral-principles.md` — always in this order:

| Rank | Signal | Question to ask |
|---|---|---|
| 1 | DM Shares | "Would someone send this to a specific person?" |
| 2 | Watch Time / Retention | "Does every second earn its place?" |
| 3 | Saves | "Would someone return to this tomorrow?" |
| 4 | Comments | "Does this demand a response?" |
| 5 | Likes | Vanity metric. Do not optimize for this. |

**The DM share test is the most important filter.** Before finalizing any blueprint, ask: who specifically is the viewer, and who do they immediately think of sending this to? If the answer is unclear, the hook or framing needs to change.

---

## THE 2026 COUNTER-TREND (always factor this in)

Hyper-editing is now the baseline, not the differentiator.

Before defaulting to:
- 1.2x zoom on frame one
- Jump cuts every 1–2 seconds
- Kinetic word-by-word text throughout
- Fast pacing throughout

Ask: **is this reference video already doing all of that?**

If the reference is hyper-edited → the user's reel should match that energy.
If the reference is raw/authentic → do NOT add hyper-editing techniques. Let the human show.

The pattern interrupt in a hyper-edited niche is stillness and direct eye contact.
The pattern interrupt in a raw/authentic niche is sharp, tight editing.

Match format to content type. Alternate between both over time.

---

## KNOWLEDGE BASE MAP (what each skill reads)

| Knowledge file | Read in stages |
|---|---|
| `viral-principles.md` | reel-blueprint, reel-review |
| `retention-playbook.md` | reel-blueprint, reel-reference, reel-capcut |
| `hook-library.md` | reel-blueprint, reel-reference |
| `text-design-system.md` | reel-blueprint, reel-capcut |
| `capcut-reference.md` | reel-capcut (ALWAYS), reel-review |
| `ugc-playbook.md` | reel-ugc (only when asked) |

---

## WHAT CLAUDE NEVER DOES

- Automatically edits video. Claude guides. User edits.
- Uses the Volcengine API. Not part of this workflow.
- Starts a reel-ugc output without reading 01-reference-breakdown.md first.
- Writes CapCut steps without checking capcut-reference.md.
- Invents a hook from a generic template. Every hook comes from the specific video's content.
- Treats likes as a meaningful optimization target.
- Applies hyper-editing techniques to a reference that is intentionally raw.
- Writes a loop close when the content delivers full value in a single pass.

---

## QUICK-START FOR ANY NEW VIDEO

1. User drops reference video anywhere inside `Desktop/I`
2. User runs `/reel-reference` → Claude finds the video, slices it into frames, reads every frame, delivers forensic analysis in conversation, deletes frames
3. User tells Claude what their video is about
4. User runs `/reel-blueprint` → Claude plans exactly how to recreate the reference with the user's content (stays in conversation)
5. User runs `/reel-capcut` → Claude writes the shoot guide (`guide.md`) + CapCut checklist (`edit-guide.html`)
6. User films following `guide.md`
7. User gives Claude the raw footage
8. User edits in CapCut following `edit-guide.html` on their phone
9. User shares finished cut → User runs `/reel-review` → Claude scores it in conversation
10. (Optional) User asks for UGC → User runs `/reel-ugc` → Claude appends UGC plan to `guide.md`
