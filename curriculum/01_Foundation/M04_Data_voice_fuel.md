# M04 — Data, your voice training fuel

> **Module 4 of 20** · Part 1: Foundation
> **Estimated time:** 45 minutes (plus the time to actually pull your data)
> **Outcome:** At least 50 of your past outputs organized into `02_Data/`, named for sortability.

## Premise

Business context tells the model *who is asking*. Data shows the model *how that person actually writes*. Without data, the model imitates the average of the internet. With data, it imitates **you**.

## Concept — How much is enough

| Output type | Minimum to start | Comfortable | Voice-locked |
|-------------|-------------------|-------------|--------------|
| Tweets / posts | 50 | 200–500 | 2,000+ |
| YouTube long-form | 3 transcripts | 5–10 | 20+ |
| Short-form video | 5 transcripts | 10–20 | 50+ |
| Newsletter / blog | 5 issues | 20 | 100+ |
| Sales / discovery calls | 2 transcripts | 10 | 30+ |

> **Don't have your own data?** Use *aspirational data*: pull transcripts from creators whose voice you want to grow into. Be honest with yourself that this is borrowed voice — not yours yet. The model will copy whoever's in the folder.

## Two organizing rules

1. **One file per piece.** Don't paste 200 tweets into one file. The model treats the file as one document. Use 200 small files instead.
2. **Sort by quality.** Best work first. The model uses file order as a soft signal of preference.

A useful naming convention:

```
02_Data/tweets/
  001_imposterSyndrome_42k_views.txt
  002_pricingMistake_19k_views.txt
  003_hiringFirstVA_8k_views.txt
  ...
```

The leading number forces the order. The middle word is a memory aid for *you*. The trailing engagement number tags the model's preference signal.

## Walkthrough — Extracting transcripts at speed

### YouTube
1. Open the video on `youtube.com` (desktop).
2. Click the `…` menu under the video → **Show transcript**.
3. Toggle timestamps off via the kebab inside the transcript panel.
4. Select all → copy → paste into a `.txt`.

### Tweets / X
1. Use a paid export tool (Twemex, Tweet Hunter, or X's data export).
2. Filter to your top quartile by engagement.
3. Save each as a numbered `.txt` with views in the filename.

### Short-form video
1. Run video files through a transcription tool (Descript, MacWhisper, whisper.cpp).
2. For other creators' content, the platform's captions usually export as `.srt`.

## Exercise — Build your starter dataset

1. Pick your highest-leverage output type. (For most operators: tweets or long-form.)
2. Get to the **minimum count** from the table above. *Non-negotiable.*
3. Save with the naming convention. The 30 minutes of file naming will pay back tenfold across every prompt run forever.
4. Drag the populated `02_Data/` folder into a Claude chat and ask: *"Read my data. In one paragraph, describe my voice as if to another writer."* Read what comes back. If it sounds like you, you're done. If not, you need more (or better) data.

**Acceptance test:** Claude's voice description matches what you'd write about your own writing.

## Knowledge check

1. Why store one tweet per file rather than all of them in one big file?
2. What's the minimum number of YouTube transcripts to start running the long-form workflow?
3. What signal does the leading number in filenames send to the model?

### Answer key

1. File-level separation gives the model 50 distinct examples instead of one document. The voice signal compounds across files.
2. Three. (Five is comfortable; twenty is voice-locked.)
3. Soft preference. The model treats earlier files as more representative of your best work, and biases output toward them.

## Takeaway

Data is the part of the system that compounds passively. Every winner you publish is a candidate to feed back into `02_Data/`. The dataset gets smarter while you sleep.

---

*Previous: [M03 — Your business context](M03_Business_context.md)* · *Next: [M05 — The anatomy of a prompt](M05_Prompt_anatomy.md)*
