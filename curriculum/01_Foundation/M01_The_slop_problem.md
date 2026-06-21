# M01 — The slop problem

> **Module 1 of 20** · Part 1: Foundation
> **Estimated time:** 30 minutes
> **Outcome:** You can explain why AI output sounds generic *and* prove the cause to yourself in a 15-minute experiment.

## Premise

Most people use AI by typing a one-line request and pasting the result. The output sounds vaguely correct, vaguely on-brand, and entirely forgettable. The internet has a name for this: **AI slop**.

Slop is not a model problem. It is an input problem. The model has nothing to anchor on except its training data — the average of the internet — so it produces the average of the internet back.

> If your AI output sounds generic, the model is not failing. *You* are.
> The fix is upstream: who is asking, what they have done before, and what they are asking for.

## Concept — Signal in, signal out

Three inputs decide the quality of every AI run:

1. **Business context** — *the who.* Who is asking, what they sell, the world they inhabit.
2. **Data** — *the past.* The author's actual prior work, which encodes voice, structure, and taste.
3. **Prompt** — *the ask.* The shape of the request: role, process, constraints, format.

Skip any one and you get slop. Provide all three and the same model that wrote the slop now writes in your voice.

## Walkthrough — Same prompt, three runs, three results

| Run | What was attached | Result (paraphrased) |
|-----|-------------------|----------------------|
| **A** | Prompt only | "Many founders underprice. Don't leave money on the table. Charge what you're worth! #startup #pricing" |
| **B** | Prompt + 1-page business context | "Charging hourly turned my agency into a busy job. The day we switched to monthly retainers, profit per hour 2.5x. Same work. Different invoice." |
| **C** | Prompt + business context + 200 past tweets | "Hourly rates put a ceiling on you. Retainers put a floor under you. Same hours. Different ladder." |

Same model. Same topic. The only thing that changed: what we attached. Run C is in the author's actual voice. Run A is the average of LinkedIn at 2pm.

## Exercise — Prove it to yourself

Block 15 minutes. Open a new chat with Claude or ChatGPT. Then:

1. **Run A.** Ask for a tweet on a topic you actually care about. Save the result.
2. **Run B.** Paste in 5 sentences describing your business. Re-ask the same prompt. Save.
3. **Run C.** Paste in 20 of your best past social posts (or emails, or Slack messages — any writing of yours). Re-ask. Save.
4. Read all three side by side.

**Acceptance test:** you can point at the sentence in Run C where the model started sounding like *you*.

## Knowledge check

1. Why does a one-line prompt produce generic output by default?
2. What are the three inputs that decide AI output quality?
3. Which of the three is the cheapest to fix today, and why?

### Answer key

1. The model has only its training data to anchor on. With no info about *who is asking*, it produces the statistical average of relevant internet writing — which is, definitionally, generic.
2. Business context (the who), data (the past), prompt (the ask).
3. Business context. It's a one-page file. You can write it in an afternoon and never write it again. Data takes weeks to collect; better prompts take iteration. Business context is the highest leverage for the lowest effort.

## Takeaway

The model isn't failing you. It's starving. The next four modules feed it.

---

*Next: [M02 — The 4-folder system](M02_Four_folder_system.md)*
