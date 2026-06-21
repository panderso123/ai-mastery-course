# M18 — The 80/20 of security for vibe coders

> **Module 18 of 20** · Part 5: Production Readiness
> **Estimated time:** 60 minutes
> **Outcome:** Your most recent build passes a 10-question pre-launch security audit.

## Premise

Most security incidents in small SaaS apps are the same handful of mistakes. Master the 80/20 and you're safer than the median paid SaaS shipping today. This module is the checklist version of the security audit prompt.

## Concept — The ten-question pre-launch audit

| # | Question | If "no," the fix |
|---|----------|------------------|
| 1 | Are all secrets in env vars (never in client code)? | Move them. Rotate any that were ever in code. |
| 2 | Is `.gitignore` actually ignoring `.env*`? | Add it. Force-push to remove history if needed. |
| 3 | Is RLS enabled on every Supabase table? | Enable. Default-deny. Add explicit policies. |
| 4 | Does every API route re-check user ownership server-side? | Add the check. Don't trust the client. |
| 5 | Is every input validated through a Zod schema? | Add schemas. Reject anything that doesn't parse. |
| 6 | Are paid third-party APIs called only from the server? | Move them. Wrap in `lib/integrations/`. |
| 7 | Are abuse-vector endpoints rate-limited per user AND per IP? | Add `@upstash/ratelimit` or equivalent. |
| 8 | Are Stripe webhooks signature-verified? | Verify. Treat the dashboard as the source of truth. |
| 9 | Are passwords / tokens / PANs scrubbed from logs? | Add a logger middleware that redacts. |
| 10 | Is there a staging environment with separate keys? | Spin one up. Test there first. |

## Concept — Defense in depth, not perimeter

Don't rely on the UI hiding a button to prevent unauthorized access. Don't rely on the API alone either. The database (RLS) is your *last* line of defense. **Every layer assumes the others will fail.**

A correct request flow has at least three checks:

1. UI button only renders if the user has the role.
2. API route re-validates the user's role server-side.
3. Database RLS policy refuses the row even if the API check is bypassed.

Any one of these can fail (a deploy bug, a stolen JWT, a logic mistake) and the others still hold the line.

## Walkthrough — Run the audit

```text
You: "Run a pre-launch security audit on this repo. For every finding, output:
      [severity: low | med | high | critical] <one-line title>
      File: <path>
      Why it matters: <1–3 sentences>
      Fix: <concrete patch>
      Use the 10-question checklist as your structure."

Agent: [walks every file, produces findings]

You: Fix every 'high' and 'critical.' Re-run. Iterate until zero of either remain.
```

The full prompt lives at Practice Kit `03_Prompts/05_security_audit.md`.

## Exercise — Audit your most recent build

1. Open the project from M14, M15, M16, or M17.
2. Run `05_security_audit.md` against it.
3. Fix every "high" and "critical."
4. Block launch on the **5-item Launch Blocker List** the prompt produces.

**Acceptance test:** the audit re-runs and produces zero "high" or "critical" findings.

> ⚠️ **Pitfall — service-role key in client code.** The single most common catastrophic mistake. The service-role key bypasses ALL Row-Level Security. If it lands in a `next.config.js` env section accidentally exposed to the browser, your entire database is wide open. Run `grep -r SERVICE_ROLE` and pray you find nothing.

## Knowledge check

1. Why does each layer assume the others will fail?
2. What's the difference between hiding a button (UI) and enforcing access (RLS)?
3. What's the single most catastrophic security mistake to avoid?

### Answer key

1. Because in production, layers do fail. Code is shipped with bugs. JWTs get stolen. Logic mistakes happen. A defense-in-depth approach means any one failure is contained, not catastrophic.
2. Hiding a button stops a *casual* user from seeing the action. Enforcing access via RLS stops *anyone* — including someone with a stolen JWT or curl access — from performing it. UI is cosmetic; RLS is enforcement.
3. Putting the Supabase service-role key (or any "admin" credential) in client-shipped code. It bypasses all per-user security and is irreversible the moment it's in browser-side JS.

## Takeaway

Security is unglamorous but cheap. An hour of audit before launch saves you from the year-long post-mortem of an incident. Run the prompt every time you ship.

---

*Previous: [M17 — Project 4: Thumbnail SaaS](../04_Building_Real_SaaS/M17_Project4_thumbnail_saas.md)* · *Next: [M19 — Deployment, monitoring, iteration](M19_Deployment.md)*
