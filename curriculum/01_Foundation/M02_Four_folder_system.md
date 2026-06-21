# M02 — The 4-folder system

> **Module 2 of 20** · Part 1: Foundation
> **Estimated time:** 30 minutes
> **Outcome:** A working `AI_Mastery/` folder on your computer that every later workflow leverages.

## Premise

Once you accept that quality output requires three inputs, the obvious question is: *where do they live?* The answer the source curriculums converge on is a flat, four-folder structure that you reuse for every AI workflow you build. Five minutes to create. Forever to keep using.

## Concept — Why this exact shape

```
AI_Mastery/
  01_Business_Context/      ← single source of truth about you/your company
  02_Data/                  ← your historical work, by content type
     tweets/
     youtube_transcripts/
     shortform_transcripts/
  03_Prompts/               ← reusable prompt templates per task
  04_Code_Projects/         ← the vibe-coded builds (Part 3 onward)
```

Three reasons the shape works:

- **Single source of truth.** Business context lives in *exactly one file*. Every prompt references it. When your offer changes, you edit one place.
- **Voice fidelity.** Data is organized by output type, not by topic, because voice differs by format. Your tweet voice is not your YouTube voice.
- **Prompt portability.** Prompts live separately from data so you can re-use the same prompt across projects with different data.

## Walkthrough — Setting it up

In your terminal:

```bash
mkdir -p AI_Mastery/{01_Business_Context,02_Data/tweets,02_Data/youtube_transcripts,02_Data/shortform_transcripts,03_Prompts,04_Code_Projects}
```

Don't have a terminal? In Finder: right-click → New Folder → name them with the exact prefixes (`01_Business_Context`, etc.). The numbers keep them sorted naturally.

Then:

1. Open a new chat with Claude (or ChatGPT, or Gemini).
2. Drag the entire `AI_Mastery/` folder into the message.
3. The model now has the entire structure as context.
4. From here on, every prompt can refer to files by name (e.g., "use the voice in `02_Data/tweets/`").

## Exercise — Set up your own kit

1. Create the folder structure above.
2. Move any existing business-related documents you have (about your company, offer, customers) into `01_Business_Context/`. Don't worry if they're messy — you'll consolidate in M3.
3. Dump your latest 50 social posts into `02_Data/tweets/` as plain `.txt` files — *one per file*.
4. Stop. The kit is the foundation. M3 fills it with the most important file in the entire system.

**Acceptance test:** you can drag the `AI_Mastery/` folder into a Claude chat and the model lists the contents back to you correctly.

## Knowledge check

1. Why is each tweet stored in a *separate* file rather than all 50 in one big file?
2. Why is data organized by output type (tweets, transcripts) rather than by topic (marketing, sales)?
3. Why does business context live in one file across all output types?

### Answer key

1. The model treats one big file as one document. Fifty separate files give it 50 anchor points to learn voice from. File-level granularity = voice-level granularity.
2. Voice differs by format. Your tweet voice isn't your YouTube voice. Topic-grouping mixes formats and degrades the voice signal.
3. Because *who you are* doesn't change between formats. Editing one file when your offer evolves is dramatically less work than editing many.

## Takeaway

Five minutes of folder creation buys you a system you'll still be using two years from now. Don't optimize the structure. Just use it.

---

*Previous: [M01 — The slop problem](M01_The_slop_problem.md)* · *Next: [M03 — Your business context](M03_Business_context.md)*
