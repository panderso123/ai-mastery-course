# M19 — Deployment, monitoring, iteration

> **Module 19 of 20** · Part 5: Production Readiness
> **Estimated time:** 45 minutes
> **Outcome:** A deploy pipeline that ships changes from `git push` to live URL, plus monitoring that pages you when things break.

## Premise

Deployment is not a one-time event. The first deploy is easy; what matters is the loop that lets you ship a fix on Tuesday at noon when a user reports a bug at 11:55. This module wires that loop.

## Concept — The pipeline

```text
git push origin main
   ↓
Netlify / Vercel / Cloudflare Pages build
   - pnpm install
   - pnpm build
   - pnpm test (if defined)
   ↓
Deploy to production URL
   ↓
Sentry / LogRocket capture errors
   ↓
User reports bug → Fix locally → PR → merge → (loop)
```

## Concept — Monitoring on day one

| Need | Tool | Why |
|------|------|-----|
| **Error capture** | Sentry | Free tier covers ~5k errors/month. Wire it up before launch, not after the first 500. |
| **Uptime** | Better Stack / BetterUptime | Ping every minute. Alert on 2 consecutive failures. |
| **Database backups** | Supabase Pro (auto) or `pg_dump` to S3 | Daily on paid; weekly on free + manual. |
| **Cost alerts** | Each paid API dashboard | Set hard limits. Get an email at 50% and 80% spend. |

## Concept — Iterating with users

1. Ship the smallest thing that solves the user's actual job.
2. Watch the **first 10 users** complete the core flow on a session-replay tool (LogRocket / OpenReplay).
3. The friction you see in those 10 sessions is your week-1 backlog. *Don't guess.*
4. Before adding any feature larger than a button, talk to **3 users on a call.**

## Walkthrough — Setting up Sentry in 5 minutes

```bash
# In your Next.js project
pnpm dlx @sentry/wizard@latest -i nextjs

# Wizard prompts you through:
# 1. Login to Sentry (sentry.io/signup if you haven't)
# 2. Pick or create a project
# 3. Auto-edits next.config.js, sentry.client.config.ts, sentry.server.config.ts
# 4. Generates a SENTRY_DSN env var

# Test it: throw new Error("test") in a route handler → check Sentry dashboard
```

Sentry is now wired. Every uncaught error in dev or prod ships to your dashboard with stack trace, browser context, and user IDs (if you set them).

## Exercise — Deploy and monitor

1. Take any project from Part 3 or Part 4.
2. Set up Sentry (5 min).
3. Set up an uptime monitor (Better Stack free tier, 2 min).
4. Set up a cost alert in your most expensive third-party API dashboard (5 min).
5. Trigger a fake error in production. Verify it appears in Sentry within 60 seconds.
6. Pause the API. Verify uptime alert pings within 2 minutes.

**Acceptance test:** all three monitoring layers fire correctly when you simulate failures.

> ⚠️ **Pitfall #1.** "I'll add monitoring later." You won't. Add it on day one or you'll debug your launch from screenshots.
>
> ⚠️ **Pitfall #2.** "My API bill quintupled overnight." You forgot the cost alert. Or the rate limit. Or both.

## Knowledge check

1. Why wire monitoring before launch instead of after?
2. What's the value of session replay for your first 10 users?
3. What's the right alerting policy for an uptime monitor on a free-tier app?

### Answer key

1. After the first incident, you have screenshots and angry users — but no error trace, no stack, no context. Wiring monitoring before launch means *the first* incident is debuggable.
2. Their friction *is* your roadmap. Without replay you guess what's confusing; with replay you watch a real human pause for 14 seconds at the same button. Pause = problem.
3. Alert on **2 consecutive failures** (not 1) to avoid noise from one transient hiccup. 1-minute interval. Slack / email + SMS for high-severity outages on paid tiers.

## Takeaway

Deployment is the easy part. The cycle of deploy → observe → fix → re-deploy is what makes a product survive contact with users. Wire the cycle before the first user arrives.

---

*Previous: [M18 — The 80/20 of security](M18_Security.md)* · *Next: [M20 — Pricing, marketing, launch](M20_Pricing_and_launch.md)*
