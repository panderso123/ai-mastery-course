---
day: 2
delay_minutes: 2880
subject: The prompt-length law (most people get this exactly backwards)
preview: Long prompts make outputs SHORTER. Here's why, and the prompt template you can copy.
from_name: AI Mastery
from_email: hi@aimastery.example.com
---

Hi {{first_name}},

Quick story.

A founder I was helping last month was on her seventh attempt at getting Claude to write a tweet that sounded like her. Each draft was worse than the last.

Her prompts were getting *longer*. The output was getting *longer too* — and worse: more generic, more hedge-y, more "the average of LinkedIn."

She had it backwards. Here's the law:

> **The longer the prompt, the SHORTER the output. The shorter the prompt, the longer the output.**

Why? Because a long, structured prompt *constrains* the model. It tells it exactly what role to play, exactly what process to follow, exactly what format to produce. There's nowhere to wander.

A short prompt is a hand-wave. The model has to guess at all of those. It guesses by producing more text — covering its bases.

Here's the structure of a real production prompt — same one I use to write tweets in my own voice:

```
You are an elite ghostwriter studying the writing of the author whose voice
is captured in the attached files. Your job has two phases.

PHASE 1 — silently build a voice profile with these sections:
  1. Voice signature (5 adjectives)
  2. Sentence rhythm (avg words/sentence; use of fragments and em-dashes)
  3. Hook patterns (5–10 opening structures the author repeats)
  4. Closer patterns
  5. Forbidden moves (things this author never does)
  6. Template library (8–12 reusable structural templates)
Do not show the profile yet. Hold it.

PHASE 2 — generate.
Topic: <<your idea here>>
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

Notice how every word does work. Role. Phases. Constraints. Format. The model has nowhere to drift.

**Try it today.** Drop that prompt into a fresh Claude chat with your business_context.md and 50 of your best past posts attached. Ask for tweets on a topic you actually want to publish about.

Compare to whatever short prompt you'd normally use.

Two days from now I'll show you what one of my students (Aman, runs an HVAC ops agency) shipped in his first week using exactly this template — including the surprising place his AI-written content landed in his sales calls.

Talk soon,
— {{sender_name}}

P.S. If you didn't do the page-6 experiment in the starter guide yet, do it before this prompt. The contrast is what makes it click.
