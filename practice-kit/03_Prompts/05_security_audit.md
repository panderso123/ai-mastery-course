# Prompt 05 — Security Audit (run before any production launch)

Paste the following into Claude Code or Antigravity, after attaching the entire repo as context.

---

You are an application security engineer doing a pre-launch audit. Treat the codebase as if it
will go live tomorrow with paying customers and PII.

## Audit checklist — go through every item, give a verdict per file

For each finding use this format:

```
[severity: low | med | high | critical] <one-line title>
File: <path>
Why it matters: <1–3 sentences>
Fix: <concrete patch or step>
```

### 1. Secrets & credentials
- Any API keys, tokens, service-role secrets in client-side code, `.env` committed to git,
  or hard-coded constants?
- Is `.gitignore` actually ignoring `.env*`?

### 2. Authentication & sessions
- Where do sessions live (cookie, JWT, Supabase auth)? HTTP-only? Secure flag?
- Is there a password reset flow, and is it rate-limited?
- Can a logged-out user reach any authenticated route?

### 3. Authorization
- Every Supabase table: does Row-Level Security exist *and* is the policy non-trivial?
- Every API route: does it re-check `userId === resource.ownerId` server-side?

### 4. Input validation
- Every API route accepts input through a Zod (or equivalent) schema before use?
- Any string interpolation into SQL? File paths? Shell commands?

### 5. Third-party APIs
- Are paid APIs (OpenAI, Stripe, scrapers) called from the client? They must not be.
- Are responses validated before being trusted?

### 6. Rate limiting & abuse
- Any endpoint that hits a paid API or sends email — is it rate-limited per user *and* per IP?
- Is there a hard daily spend cap on third-party calls?

### 7. Payments (if Stripe / similar)
- Is the webhook signature verified?
- Is the order/subscription state derived from the webhook, not from the client redirect?

### 8. Logging & PII
- Are passwords, tokens, or full credit card numbers ever logged? (Even on errors.)
- Is there an error-reporting service, and is it scrubbing PII?

### 9. Dependencies
- Run `pnpm audit`. Anything `high` or `critical`? Any package not maintained in 2+ years?

### 10. Build & deploy
- Are environment variables actually set in Netlify / Vercel for production?
- Is there a staging environment with separate keys?

## Output

End with a 5-item **Launch Blocker List** — the items that, if not fixed, mean we do not ship.
