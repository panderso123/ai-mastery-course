# M16 — Project 3: Lead-gen SaaS

> **Module 16 of 20** · Part 4: Building Real SaaS
> **Estimated time:** 6–10 hours of build time
> **Outcome:** A SaaS that takes payment, runs an async job against a third-party API, and writes results to a dashboard the user can export.

## Premise

This is the first build that has the shape of a sellable SaaS: external API integrations, async jobs, and Stripe-gated usage. Plot it in any vertical you understand — the source curriculum uses HVAC contractors targeting commercial property managers; the pattern transfers to law firms, dental offices, accountants, anyone with a defined buyer.

## Architecture sketch

```text
User submits LeadJob{industry, region, count, persona}
   ↓
Next.js API route validates with Zod, decrements lead-credits in DB
   ↓
Insert row in lead_jobs (status = pending)
   ↓
Supabase Edge Function on 30s cron drains queue
   ↓
Calls scraping API (Apollo / Apify) → enrichment API (Hunter)
   → generate first-touch email via Claude API
   ↓
Writes rows to leads table with personalized_email
   ↓
Dashboard polls or subscribes; user reviews + exports CSV
```

## Walkthrough — Step by step

1. **Spec the app** with Practice Kit's `06_idea_to_spec.md`. Pay special attention to: rate limits, cost per call, abuse vectors.
2. **Build auth + billing first.** Nothing else matters if you can't take money. Use Stripe metered billing.
3. **Wire the LeadJob form.** Validate everything with Zod. Decrement credits in the same transaction that creates the job.
4. **Build the queue table** (`lead_jobs`) and the worker (Edge Function). Keep it simple: no Redis, no SQS.
5. **Wrap third-party APIs** in `lib/integrations/*` so the rest of the app never imports their SDKs directly. Easier to swap later.
6. **Generate personalized emails** via Claude API. Attach `business_context.md` to every call.
7. **Build the dashboard:** job history, status pills, leads table, CSV export, "regenerate email" button.
8. **Run Practice Kit's `05_security_audit.md`** against the repo. Fix every "high" and "critical." Then ship.

## Pricing scaffold

| Plan | $/mo | Lead credits | Overage |
|------|------|--------------|---------|
| Starter | $49 | 100 | $0.75 each |
| Growth | $149 | 500 | $0.50 each |
| Scale | $399 | 2,000 | $0.35 each |

Tune pricing after you talk to your first 5 paying users. Anything you decide today is a guess.

## Exercise — Build the project

This one's a full weekend, plausibly two. Don't try to do it in one sitting. Suggested split:

- **Day 1 (4 hrs):** Auth + billing + dashboard scaffold.
- **Day 2 (4 hrs):** Queue table + worker + first integration.
- **Day 3 (2 hrs):** Email generation + security audit + deploy.

> ⚠️ **Pitfall — runaway API costs.** Forget the per-user-per-day spend cap and your first viral user blows up your bill in 90 minutes. Add the cap on day 1, not after the bill arrives.
>
> ⚠️ **Pitfall — abuse vectors.** Rate limit by user *and* IP. Both. Always.
>
> ⚠️ **Pitfall — Stripe billing drift.** Always derive subscription state from Stripe webhooks, not the success-page redirect. Customers will close the tab before the redirect; webhooks are the source of truth.

## Knowledge check

1. Why is auth + billing the first feature to build, not the dashboard?
2. Why wrap every third-party SDK in `lib/integrations/*`?
3. How do you protect yourself from a viral user blowing up your API bill?

### Answer key

1. Without auth + billing, no feature you build can be sold. Building the dashboard first means a working app you can't charge for. Money-taking infra is the foundation.
2. Vendor risk. The scraping API may change pricing, terms, or shut down. The wrapper means you swap the integration in one place rather than across the codebase.
3. Per-user-per-day spend cap *plus* per-user-and-per-IP rate limit *plus* a hard daily total cap configured in the third-party dashboard itself. Three layers because any single one can fail.

## Takeaway

The first SaaS you ship will not be the one that makes money. The point is the muscle: integrating APIs, running async jobs, taking payments, surviving abuse. Once you've done that pattern once, the next ten projects compress to a weekend each.

---

*Previous: [M15 — Project 2: Client dashboard](M15_Project2_dashboard.md)* · *Next: [M17 — Project 4: Thumbnail SaaS](M17_Project4_thumbnail_saas.md)*
