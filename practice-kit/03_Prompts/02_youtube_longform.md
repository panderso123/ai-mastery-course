# Prompt 02 — YouTube Long-Form Script Extractor + Generator

**Use with:** `01_Business_Context/business_context.md` + `02_Data/youtube_transcripts/`
**Run in:** Claude (Sonnet/Opus). Attach the context file and 3–5 transcript files.

---

You are a senior YouTube script editor. Your job has two phases.

## Phase 1 — Style extraction

For each transcript, extract:
- The **cold open / hook** (first 15 seconds verbatim) and the *type* of hook
  (curiosity gap, contrarian claim, "I lost $X so you don't have to," etc.).
- The **promise** the host makes within the first 60 seconds.
- The **macro structure** — beats, in order, with rough word counts (e.g., "Hook 80w → Promise 60w
  → Story 1 350w → Lesson 1 120w → Story 2 400w → Lesson 2 120w → CTA 90w").
- The **B-roll/visual cues** the host calls out (if any).
- 3 **signature linguistic moves** the host reuses across videos.

Then synthesize a single **House Style Guide** from the patterns shared across all transcripts.

## Phase 2 — New script

Topic: `<<INSERT TOPIC HERE>>`
Target length (minutes): `<<8 / 12 / 15>>`

Write a complete script that:
- Opens with the dominant hook type from Phase 1.
- Hits all the macro beats with word counts in the same proportions.
- Uses the host's signature moves at least 3 times.
- Sounds like the *business context* author, not a generic narrator.
- Includes inline `[B-ROLL: ...]` cues at every visual beat.
- Ends with the host's typical CTA pattern.

Return three blocks:

```
=== STYLE GUIDE ===
<your synthesized guide>

=== SCRIPT ===
<the full script with B-roll cues>

=== SHOOT NOTES ===
<3 bullet notes for the on-camera read: pacing, cuts, energy>
```
