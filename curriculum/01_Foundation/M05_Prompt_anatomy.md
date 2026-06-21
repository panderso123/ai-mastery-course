# M05 — The anatomy of a prompt

> **Module 5 of 20** · Part 1: Foundation
> **Estimated time:** 45 minutes
> **Outcome:** You can read a production-grade prompt and explain *why each section is there.* You'll have rewritten one of your own prompts at least 3x longer and more effective.

## Premise

If business context is *the who* and data is *the past*, the prompt is *the ask*. It is the most underrated lever in the entire stack — because most people treat prompts like search queries instead of like specifications.

> The longer the prompt and the more specific the prompt, the better the output the AI is going to have.
> *— the prompt-length law*

> The longer the prompt, the shorter the output. The shorter the prompt, the longer the output.
> *— the prompt-length corollary*

Sounds wrong. Then you watch it happen.

**Why?** A long, structured prompt *constrains* the model. It tells it exactly what role to play, exactly what process to follow, exactly what format to produce. There's nowhere to wander. A short prompt is a hand-wave; the model has to guess at all of those, and it guesses by producing more text — covering its bases.

## Concept — The six prompt levers

| Lever | Why it works | Practical move |
|-------|--------------|----------------|
| **Length** | Long prompts constrain output; short prompts let it wander. | Aim for 300–800 word prompts for any real task. |
| **Role** | Sets evaluation criteria implicitly. | "You are an elite [discipline] doing [task] for [audience]." |
| **Process** | Forces step-by-step reasoning before output. | Phase 1 / Phase 2 / Phase 3 sections inside the prompt. |
| **Examples** | Few-shot beats zero-shot every time. | Attach 3–5 of your best past outputs. |
| **Constraints** | Negative space defines the result. | "No emoji. No hashtags. No exclamation points." |
| **Format** | Locks output shape so you can compare runs. | "Return JSON with keys X, Y, Z" or use a fixed template. |

## Walkthrough — One-line vs one-page

### The 1-liner

```text
Write me a tweet about productivity.
```

This produces a 280-character platitude. The model has no other choice.

### The 1-pager (annotated)

```text
You are an elite ghostwriter studying the writing of the author whose voice
is captured in the attached files. Your job has two phases.

PHASE 1 — silently build a voice profile with these sections:
  1. Voice signature (5 adjectives)
  2. Sentence rhythm (avg words/sentence; use of fragments, em-dashes)
  3. Hook patterns (5–10 opening structures the author repeats)
  4. Closer patterns
  5. Forbidden moves (things this author never does)
  6. Template library (8–12 reusable structural templates)
Do not show the profile yet. Hold it.

PHASE 2 — generate.
Topic: productivity for solo founders.
Number of drafts: 4.
Constraints:
  - Each draft uses a different template from the library.
  - Each draft is on-topic, not generic motivation.
  - No emoji. No hashtags. No "in conclusion" energy.
  - Match the median tweet length of the author's data.

PHASE 3 — return format.
For each draft:
  DRAFT N — template: <name>
  <the post>
After all drafts, output a one-paragraph Voice Audit — brutal.
```

Every word does work. Role. Phases. Constraints. Format. The model has nowhere to drift.

This is the actual production prompt that ships in the AI Mastery Practice Kit (`03_Prompts/01_tweet_generator.md`).

## Exercise — Rewrite your worst prompt

1. Pick the AI prompt you've used most this past week.
2. Paste it into a new file. Read it as if a stranger wrote it. (It probably reads as a hand-wave.)
3. Add: a **role**. A **3-phase process**. **Constraints**. A **fixed output format**.
4. Run both versions on the same input. Compare outputs side by side.

**Acceptance test:** the long-prompt output is shorter, more on-voice, and easier to evaluate as "ship / don't ship" than the short-prompt output.

> ⚠️ **Pitfall — random length is worse than short.** If you stack instructions without structure, the model ignores half. Use Phase 1 / Phase 2 / Phase 3 to give it handles. Length without structure = noise.

## Knowledge check

1. State the prompt-length corollary.
2. What does the "Phase 1 / Phase 2 / Phase 3" structure do that a flat instruction list doesn't?
3. Why does asking for a self-audit at the end of the prompt improve output quality?

### Answer key

1. The longer the prompt, the shorter the output. The shorter the prompt, the longer the output.
2. It forces sequential reasoning. The model commits to a plan (Phase 1) before generating (Phase 2) before formatting (Phase 3). Flat instruction lists let the model interleave and skip — usually skipping the analysis step.
3. Self-audit catches drift in the same call. The model has to articulate why each draft is on/off — which surfaces problems you would otherwise need a second prompt to find.

## Takeaway

Prompts are specifications, not search queries. Length is your friend when length has structure. **Steal the production prompt above** as your starting template; rewrite it once a quarter as your taste evolves.

---

*Previous: [M04 — Data, your voice training fuel](M04_Data_voice_fuel.md)* · *Next: [M06 — The tweet generation loop](../02_Content_Workflows/M06_Tweet_loop.md)*
