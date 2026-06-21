# M06 — The tweet generation loop

> **Module 6 of 20** · Part 2: Content Workflows
> **Estimated time:** 45 minutes
> **Outcome:** A 7-day batch of polished, on-voice tweets ready to schedule.

## Premise

Tweets (and their LinkedIn / Threads cousins) are the highest-volume, lowest-stakes place to apply the framework. They're also the fastest feedback loop you have: post, watch, learn. This is the workflow you'll use most often — let's lock it in.

## Concept — The end-to-end loop

| # | Step | What you do |
|---|------|-------------|
| 1 | **Topic ideation** | Bring 1–3 ideas in your own head. The model never originates. |
| 2 | **Attach inputs** | `business_context.md` + 50–200 of your top tweets + the tweet-generator prompt. |
| 3 | **Generate 4 drafts** | Run the tweet prompt from your Practice Kit. |
| 4 | **Voice audit** | Use the prompt's self-critique section to catch off-voice drafts. |
| 5 | **Human edit** | Tighten, swap one verb, kill any AI tells ("dive in", "unlock", "game-changer"). |
| 6 | **Schedule + measure** | Schedule across the week. Tag winners. |
| 7 | **Feed back** | Add the winning tweets to `02_Data/tweets/`. The dataset improves. |

## Walkthrough — One topic, four drafts

**Topic:** "Why hourly billing kills agencies."

You run the tweet prompt with `business_context.md` + 200 past tweets attached. A representative slice of what comes back:

```text
DRAFT 1 — template: rule + counter-rule
  Hourly rates put a ceiling on you.
  Retainers put a floor under you.
  Same hours. Different ladder.

DRAFT 2 — template: 75% threshold
  75% of agency owners I meet still bill hourly.
  75% of them are stuck under $30k/mo.
  Coincidence? No.

DRAFT 3 — template: numbered teach
  Three reasons hourly kills agencies:
  1. It rewards slowness.
  2. It anchors clients to your cost, not their outcome.
  3. It punishes your best people for being fast.

DRAFT 4 — template: imperative stack
  Stop billing hourly.
  Start billing per outcome.
  Watch your best month happen by accident.

VOICE AUDIT — Drafts 1 and 4 land closest to the data set's sentence rhythm.
Draft 2 is on-voice but the stat is fabricated; remove unless verified.
Draft 3 is too "linkedin-explainer"; cut.
```

> ✅ **Win pattern.** The model flags its own fabrication in Draft 2. That's the value of the self-audit phase. Always include it in the prompt.

## Exercise — Your first 7-day batch

1. **Brainstorm 7 topics** on a notepad — one per day.
2. Run the tweet prompt for **all 7 topics** (4 drafts each → 28 drafts).
3. Pick **1 from each topic.** Edit each by hand for 5 minutes.
4. Schedule across 7 days using your scheduler of choice (Buffer, Hypefury, X native).
5. After the week, copy the **top 3 by engagement** back into `02_Data/tweets/`. Your dataset just got smarter.

**Acceptance test:** at least 5 of the 7 tweets feel like *you* would have written them on your best day.

## Knowledge check

1. Why ask for 4 drafts instead of 1?
2. What single line in the prompt catches a fabricated statistic before publication?
3. Why feed winners back into `02_Data/tweets/`?

### Answer key

1. Diversity surfaces structure. Four templates running on the same topic show you which patterns suit *this* topic. Iteration that costs almost nothing is iteration you should do.
2. The self-audit / Voice Audit closing instruction in the prompt. The model has to articulate *why* each draft is on or off — fabrications surface here.
3. Compound interest. The dataset is the moat. Every published winner makes the next generation smarter. Most students miss this step and wonder why their output plateaus.

## Takeaway

Tweets are practice. Cheap, frequent, low-stakes. Run the loop weekly for 8 weeks before judging the system. The compound shows up around week 4.

---

*Previous: [M05 — The anatomy of a prompt](../01_Foundation/M05_Prompt_anatomy.md)* · *Next: [M07 — Long-form: YouTube and blog](M07_Long_form.md)*
