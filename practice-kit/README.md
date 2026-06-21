# AI Mastery Practice Kit

This kit is the workbench for the **AI Mastery Practice Manual** (`AI_Mastery_Practice_Manual.docx`).
It is a deliberately minimal scaffold — the same `business_context / data / prompts` pattern that
sits at the core of both source modules — plus three starter projects you build through the manual.

```
AI_Mastery_Practice_Kit/
├── 01_Business_Context/      # The single source of truth about you/your company.
├── 02_Data/                  # Your historical work — voice training fuel.
│   ├── tweets/
│   ├── youtube_transcripts/
│   └── shortform_transcripts/
├── 03_Prompts/               # Reusable prompt templates per content type.
├── 04_Code_Projects/         # Hands-on builds from the vibe-coding chapters.
│   ├── portfolio/
│   ├── dashboard/
│   └── saas_lead_gen/
└── 99_Reference/             # Cheat sheets you will pull from often.
```

## How to use it

1. Open `01_Business_Context/business_context.md` and fill in every field.
   Until that file is real, nothing downstream will sound like you.
2. Drop your historical content into the matching `02_Data/...` folder.
   Keep filenames sortable by performance (e.g., `001_tweet_42k_views.txt`).
3. Open the relevant prompt in `03_Prompts/` and follow the manual's
   step-by-step generation loop (Chapters 4–6).
4. When you reach the vibe-coding chapters, the empty project folders in
   `04_Code_Projects/` already match the manual's exercises.

## The contract with yourself

> Every output you ship will reference exactly **one** business context file,
> exactly **one** data set, and exactly **one** prompt. If a result feels
> generic, the fix is upstream — not in the AI.
