# Project 3 — Lead-Gen SaaS (third-party APIs, async jobs, Stripe)

This project corresponds to **Manual, Chapter 13**.

## Scenario
A vertical lead-generation SaaS. The user picks an industry + region + lead count; the app
scrapes, enriches, queues a personalized email, and shows results in a dashboard. Stripe
gates the lead-fetch action behind a usage-based plan.

## Starter prompt
> Build a SaaS using the standard vibe-coding stack. Domains:
>
> 1. **Auth & billing.** Supabase Auth + Stripe (subscription with metered usage —
>    "lead credits"). Webhook-driven; the client never decides if a user has credits.
> 2. **Lead jobs.** A user submits a `LeadJob{industry, region, count, persona}`. The
>    backend enqueues a job (use a Postgres-backed queue table — keep it simple, no Redis).
>    A scheduled function (Supabase Edge Function on a 30s cron) drains the queue, calls
>    a scraping API (Apollo, Apify — pick one, document choice), enriches with email
>    finder, stores results in `leads`.
> 3. **Outreach drafts.** For each lead, generate a personalized first-touch email via
>    Claude API, scoped by the user's `business_context.md` and `tone_guide.md`.
> 4. **Dashboard.** Job history, status badges, leads table with CSV export, "regenerate
>    email" button.
>
> Apply `04_vibe_coding_rules.md`. Run `06_idea_to_spec.md` first; wait for my answers
> on the open questions before writing code.

## Pre-launch
Run `05_security_audit.md` against the repo. Block launch on every "high" or "critical."

## Pricing scaffold (default; tune after talking to 5 users)
| Plan | $/mo | Lead credits | Overage |
|---|---|---|---|
| Starter | $49 | 100 | $0.75 each |
| Growth  | $149 | 500 | $0.50 each |
| Scale   | $399 | 2,000 | $0.35 each |
