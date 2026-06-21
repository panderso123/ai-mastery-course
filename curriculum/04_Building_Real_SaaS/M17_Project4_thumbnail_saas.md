# M17 — Project 4: Thumbnail generator SaaS

> **Module 17 of 20** · Part 4: Building Real SaaS
> **Estimated time:** 4–8 hours
> **Outcome:** A SaaS that takes a video title (and optionally a still), produces multiple AI-generated thumbnails, and lets the user download the winner.

## Premise

The fourth build mixes vision-capable LLMs with image generation. The product takes a video title (and optionally a still or a description) and returns multiple on-brand thumbnail options. Concentrated audience (creators, marketers), known unit economics, vocal early adopters — a great fourth build.

## Architecture sketch

```text
User uploads video metadata + optional still
   ↓
API route: validate input, debit credits
   ↓
Claude (vision) extracts: subject, mood, dominant color, suggested text overlay
   ↓
Generate 3 design briefs (variant: bold, variant: minimal, variant: cinematic)
   ↓
For each brief: call image API (DALL·E / SDXL / Midjourney via API)
   ↓
Compose final image: AI-generated background + overlay text rendered server-side
   ↓
Return 3 PNG URLs to the dashboard for download / regenerate
```

## Why this is a great fourth build

- Two AI modalities (text + image) plus binary file storage (Supabase Storage).
- Unit economics are easy to model: cost-per-thumbnail is known; markup is your margin.
- Audience is concentrated and vocal — great for early feedback.

## Walkthrough — Step by step

1. **Run `06_idea_to_spec.md`** to spec. Pin the open questions (which image API, single still vs multi-frame).
2. **Add Supabase Storage** for the final PNGs. Bucket: `thumbnails`. RLS so users only see their own.
3. **Wrap each external service** in `lib/integrations/`. The image API choice should be one config change.
4. **Build the dashboard:** history of generated thumbnails with one-click regenerate.
5. **Add a "teach my style" step:** user uploads 5–10 reference thumbnails. Use these as few-shot examples to bias generations.
6. **Run `05_security_audit.md`.** Pay extra attention to file upload validation — size, type, dimensions.

## Exercise — The validation lap (do this *before* building)

Before you write a line of code:

1. Find **5 YouTube creators** who would plausibly pay $19–49/mo for this.
2. Email them. Describe the product in 2 sentences. Ask if they'd want it.
3. If **3+ reply with interest**, build it.
4. If **0 reply**, something about your positioning is wrong — fix that before fighting the model.

This rule applies to every SaaS you'll ever build. The cost of building first is enormous; the cost of emailing 5 people is zero.

## Knowledge check

1. Why do the validation lap *before* writing any code?
2. Why is Supabase Storage the right place for the final thumbnails (vs storing in Postgres or returning as base64)?
3. What's the role of the "teach my style" step and which prompt-engineering lever does it pull?

### Answer key

1. The most expensive code is code nobody wants. Five emails is an hour; a built-and-launched-and-flopped SaaS is a month. Validate first.
2. Postgres can store binary but it's a bad fit (slow reads, expensive backups). Base64 in JSON is bigger than the binary itself. Object storage with a CDN is the right tool.
3. It's the **examples** lever (few-shot). Showing the model 5–10 thumbnails the user actually likes biases generation toward that aesthetic — far more powerful than describing the aesthetic in words.

## Takeaway

The thumbnail SaaS is the build where you'll feel the leverage of the system the most: business context (the user's brand) + data (their reference thumbnails) + prompts (the structured generation flow). Same framework as Part 1 — applied to images.

---

*Previous: [M16 — Project 3: Lead-gen SaaS](M16_Project3_lead_gen_saas.md)* · *Next: [M18 — The 80/20 of security](../05_Production_Readiness/M18_Security.md)*
