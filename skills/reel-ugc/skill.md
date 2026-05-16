# Skill: reel-ugc

## Purpose
Add a UGC layer to the reel — but derived entirely from the reference video's DNA. Not from Claude's default UGC training. Only runs when the user explicitly asks.

## Trigger
User explicitly says "add UGC", "give me a UGC version", or "UGC angle" for this reel.

## ⚠️ STOP — Read this before anything else

Claude's default UGC patterns are BANNED in this system:
- Talking-head honest review to camera
- Unboxing / first impression format
- "I tried this for 30 days" testimonial
- Lifestyle b-roll + voiceover
- "POV: you just discovered..." caption style
- Green-screen product overlay

**None of these are acceptable.** Do not reach for them. Do not suggest them.

The only acceptable source for the UGC angle is the reference analysis in the current conversation context.

## What to read BEFORE starting
1. Conversation context — the reference analysis from `/reel-reference` (THIS IS THE ONLY SOURCE. Read the Reference DNA Summary carefully.)
2. Conversation context — the blueprint decisions from `/reel-blueprint`
3. If this is a new session with no reference analysis in context: tell the user to run `/reel-reference` first to get the analysis back into the conversation before proceeding.
4. Conversation context — target viewer and goal (from reel-new intake)
5. `knowledge/ugc-playbook.md` — full derivation rules and what makes UGC feel real in 2026

## What to do

### Step 1 — Map the reference structure EXACTLY

From the reference analysis in conversation context, extract the shot-by-shot structure as a table:

| Timestamp | What happens visually | Format/technique used |
|---|---|---|
| [Xs–Ys] | [exact visual description] | [split-screen / screen-recording / close-up / etc.] |

This is your recreation template. Every row must have an equivalent in the user's content.

### Step 2 — Fill each segment with the user's content

For each reference segment, ask: **"What is the [user's content] version of this exact visual?"**

Not: "What's a good way to introduce the topic?"
Not: "What hook works for this niche?"

The question is only: "If @[creator] were making a reel about [this user's subject], what would THIS EXACT SEGMENT look like?"

Rules:
- The format (split-screen, overhead, close-up, etc.) does NOT change — only the content inside it changes
- If the reference uses split-screen → the UGC version uses split-screen
- If the reference uses a tutorial-on-a-surface shot → the UGC version uses the same shot for the user's subject
- If the reference loops back to its hook → the UGC version loops back to its hook

### Step 3 — Identify what you genuinely cannot recreate and substitute cleanly

Some reference segments may not translate to the user's content. Find the closest structural substitute and note the substitution explicitly so the user understands what changed and why.

### Step 3 — Apply the "feels real" test

Before writing anything, check that the UGC angle passes:

- [ ] Would an actual person film this? (not a brand, not an actor — a real person)
- [ ] Does the framing feel imperfect and real, not suspiciously clean?
- [ ] Does every line of dialogue pass the "I would actually say this" test?
- [ ] Is the environment believable (not staged)?
- [ ] Does it signal "real person" in a feed of produced content?

If any check fails → rethink the angle.

### Step 4 — Write the UGC layer

```markdown
## UGC Angle
[One paragraph: what this UGC looks like, why it fits the reference's DNA, what makes it feel real — NOT a template name]

## The Hook (0–3s)
Visual: [exact description of what's filmed and from what angle]
Audio: [what's said, or ambient sound, or no speech]
Text: [exact text if any, or "none"]
What stops the scroll: [the specific pattern interrupt]

## Shot List
Shot 1 — [timestamp range]
  What's filmed: [exact description]
  Angle/distance: [handheld? POV? close-up?]
  Dialogue (if any): "[exact words]"
  Text overlay (if any): "[text]"

Shot 2 — [timestamp range]
  [same format]

[... every shot]

## What Makes It Feel Real
[Specific choices that prevent this from looking like produced UGC:]
- [Imperfection strategy — e.g. "slightly off-center framing, no ring light"]
- [Speech pattern — e.g. "one hesitation mid-sentence, not scripted delivery"]
- [Environment — e.g. "kitchen counter background, not clean backdrop"]

## CapCut Edit Notes
How to edit this UGC in CapCut to match the reference's pacing and style:
[Reference knowledge/capcut-reference.md for all tap paths]
- Cut rhythm: [every Xs]
- Transitions: [type or none]
- Text style: [match reference's font/color/position or specify why different]
- Audio: [original audio? music? volume levels?]
- Color: [filter + manual adjustments to match reference's look]
```

## Output
Append the UGC layer to `projects/[video]/guide.md` as a new section:
```
## Part 3: UGC Version
[the full UGC output from Step 4]
```

## Rules
- If the reference analysis from `/reel-reference` is not in the current conversation context, stop and tell the user to run `/reel-reference` first. Do not proceed without it.
- Do not read `01-reference-breakdown.md` — that file no longer exists in this system.
- Never name a generic UGC format as the angle.
- The angle description must be specific enough that someone reading it knows exactly what to film — not "authentic talking head" but "standing at kitchen counter, phone propped against a glass, mid-sentence when the clip starts."
- CapCut edit notes must reference `knowledge/capcut-reference.md` tap paths.
