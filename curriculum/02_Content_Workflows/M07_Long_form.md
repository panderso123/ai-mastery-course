# M07 — Long-form: YouTube and blog

> **Module 7 of 20** · Part 2: Content Workflows
> **Estimated time:** 60 minutes (plus the writing of one full script)
> **Outcome:** A House Style Guide you keep, and one ready-to-record long-form script.

## Premise

Long-form output (8–20 minute video scripts, 1,500+ word essays) is where AI assistance scales differently. A tweet is a one-shot generation. A long-form piece is a **structure problem first** and a sentence problem second.

## Concept — The script as a graph, not a paragraph

The model is excellent at recognising and reproducing structure once you show it the structure. So your prompt has two phases:

1. **Extract** the structure of work you admire.
2. **Generate** new content that fills the same skeleton with *your* ideas.

## Walkthrough — End-to-end

1. Pick **3–5 videos** from creators whose structure you want to inherit. Pull transcripts (M4 covered the technique).
2. Run the long-form prompt (Practice Kit `03_Prompts/02_youtube_longform.md`). Phase 1 produces a **House Style Guide.**
3. Read the style guide. Edit it. **This document you keep.** It does not need to be regenerated each time.
4. Phase 2 generates the script for *your* topic. Iterate 2–3 times before recording.
5. After publishing, add your own transcript back into `02_Data/youtube_transcripts/` to deepen the dataset.

**Sample House Style Guide output (excerpt):**

```text
=== HOUSE STYLE GUIDE ===
Dominant hook: contrarian past-tense ("I used to think X. I was wrong.")
Macro structure (12-min target):
  Hook 80w → Promise 60w → Story 1 350w → Lesson 1 120w →
  Story 2 400w → Lesson 2 120w → Counter-take 200w → CTA 90w
Signature moves:
  - "Here's the part nobody tells you" (mid-script callback)
  - Cold-open visual that recurs at the close
  - Closing one-liner that rhymes with the hook
B-roll: every story beat gets a [B-ROLL: receipt / screenshot / whiteboard] cue.
```

That style guide is reusable across hundreds of future scripts. Generating one for *each* video is wasteful. Generate it once. Reuse it.

## Exercise — Produce one ready-to-record script

1. Choose your **3–5 source creators**. Pull transcripts.
2. Run the long-form prompt. Save the **House Style Guide** as a separate file in `03_Prompts/` — you'll reuse it.
3. Edit the generated script:
   - Cut 10% from every section. (AI scripts run long.)
   - Add 1 personal anecdote the model couldn't have known.
4. Record. Don't over-engineer the first one. Ship.

**Acceptance test:** you finish the script in one sitting and know the first three sentences without reading them.

> ⚠️ **Pitfall.** Don't pick *only* big-channel creators as references. The structures that work for a 2M-subscriber creator assume hooks aimed at a fully cold audience. If your audience is warm and small, mix in 1–2 creators at your scale.

## Knowledge check

1. Why is the House Style Guide a *kept* artifact rather than something you regenerate per script?
2. Why does the prompt extract structure before generating?
3. Why cut 10% from every section before recording?

### Answer key

1. Style decisions compound. Once the guide reflects your taste (after you edit it once), regenerating it from scratch each time would invite drift. Save it; iterate on it manually as your taste evolves.
2. Models recognize and reproduce structure they've been shown. Showing structure first locks the skeleton, then generation fills the skeleton — instead of letting the model invent both.
3. AI-generated long-form runs ~10% long because the model hedges. Cutting forces tighter prose and shorter videos, both of which hold attention better.

## Takeaway

For long-form, the prompt is half the system. The other half is the House Style Guide you keep, edit, and reuse. Treat the guide like code: version it, evolve it, never throw it away.

---

*Previous: [M06 — The tweet generation loop](M06_Tweet_loop.md)* · *Next: [M08 — Short-form: Reels, Shorts, TikTok](M08_Short_form.md)*
