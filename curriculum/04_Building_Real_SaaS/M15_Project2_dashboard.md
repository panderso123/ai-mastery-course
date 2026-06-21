# M15 — Project 2: Client dashboard (full-stack)

> **Module 15 of 20** · Part 4: Building Real SaaS
> **Estimated time:** 4–6 hours of focused build time
> **Outcome:** A deployed full-stack dashboard with auth, two roles, real-time updates, and row-level security.

## Premise

This is your first full-stack build. The scenario is a content-writing agency: clients log in to see articles in progress, leave notes, and approve. The pattern generalises to any agency-style SaaS — design, video, accounting, consulting.

## Scope

- **Roles:** `client` and `writer`.
- **Tables:** `accounts`, `articles` (status: draft / in_review / approved / published), `notes`.
- **Auth:** Supabase magic links. No password handling on day one.
- **Real-time:** status changes and new notes appear without refresh.
- **Security:** every table has Row-Level Security; service-role keys never reach the client.

## Walkthrough — Step by step

### Step 1 — Spec it
Run Practice Kit's `06_idea_to_spec.md` with the dashboard scenario. Wait for the model's open questions. Answer them. Get a clean spec before any code.

### Step 2 — Scaffold

```bash
pnpm create next-app@latest dashboard --ts --tailwind --app --eslint --src-dir
cd dashboard
pnpm add @supabase/supabase-js @supabase/ssr zod
npx shadcn@latest init
npx shadcn@latest add button input card dialog table
```

### Step 3 — Supabase

1. Create a Supabase project. Copy `SUPABASE_URL` and `ANON_KEY` into `.env.local`.
2. Create the tables via the SQL editor (or `supabase/migrations/0001_init.sql`).
3. **Enable RLS on every table.** Add policies (write them via the agent; review every one).
4. Test policies: sign in as user A, try to query user B's rows. Expect zero results.

### Step 4 — Ship the prompt

Hand the prompt from Practice Kit's `04_Code_Projects/dashboard/PROMPT.md` to the agent. Insist on **"spec first, then code."** Review every migration.

## Definition of done

- A second browser, signed in as the client, sees the writer's status change within 2 seconds.
- Direct-URL access to another account's article returns **404** (RLS, not just UI hide).
- All three Supabase tables have at least one RLS policy.
- Service-role keys live only on the server; the client only ever sees the anon key.
- Lighthouse Best Practices ≥ 95.

## Exercise — Build the project

Time-box: 4 hours over 2 sittings. Don't add features beyond the scope. The discipline of *not adding features* is part of the lesson.

> ⚠️ **Pitfall #1 — RLS in dev vs prod.** "It works in dev but RLS blocks me in prod." You probably tested with the service-role key locally. Always test with the anon key + a real session.
>
> ⚠️ **Pitfall #2 — destructive migrations.** "The agent wrote a migration that drops a column." Migrations are forever. Read every line. Never run a migration the agent generated without re-reading it.

## Knowledge check

1. Why use magic links instead of passwords for auth on day one?
2. What's the difference between hiding a UI element and enforcing access via RLS?
3. Why should the service-role key never reach the client?

### Answer key

1. Magic links eliminate password storage, password reset flows, password leak risk, and most onboarding friction. You add real password auth later if needed.
2. UI hiding is cosmetic — anyone with the API can bypass it. RLS is enforced by the database itself: even with a stolen JWT, the database refuses to return rows the user doesn't own. Defense in depth.
3. The service-role key bypasses ALL RLS. If it lands in client JavaScript, the entire database is wide open to any visitor with browser dev tools.

## Takeaway

Project 2 is the first time the agent writes code that real users could rely on. Every RLS policy you skip becomes a bug bounty waiting to be found.

---

*Previous: [M14 — Project 1: Portfolio site](../03_Vibe_Coding_Fundamentals/M14_Project1_portfolio.md)* · *Next: [M16 — Project 3: Lead-gen SaaS](M16_Project3_lead_gen_saas.md)*
