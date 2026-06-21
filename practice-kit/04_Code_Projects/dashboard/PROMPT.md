# Project 2 — Client Dashboard (full-stack, auth, real-time)

This project corresponds to **Manual, Chapter 11**.

## Scenario
You run a content-writing agency. Clients log in, see a queue of articles in progress, leave
notes, and approve or request changes. Writers (you) push status updates. Real-time so the
client doesn't have to refresh.

## Starter prompt
> Build a full-stack dashboard with Next.js App Router + TypeScript + Tailwind +
> shadcn/ui + Supabase. Roles: `client` and `writer`. Tables (with RLS):
> `accounts(id, name, owner_user_id)`,
> `articles(id, account_id, title, status [draft|in_review|approved|published], body_md, due_at)`,
> `notes(id, article_id, author_user_id, body, created_at)`.
>
> Pages:
> - `/login` — Supabase magic link.
> - `/dashboard` — list of articles for the signed-in user's account, filterable by status.
> - `/articles/[id]` — markdown preview, status pill, notes thread (real-time via Supabase
>   channel), action buttons (writers only: change status; clients only: leave note + approve).
>
> Apply the house rules in `03_Prompts/04_vibe_coding_rules.md`.
>
> First output the spec (using `06_idea_to_spec.md` template), wait for me to confirm,
> then generate the migrations and code.

## Definition of done
- A second browser, logged in as the client, sees the writer's status change within 2 seconds.
- Direct-URL access to another account's article returns 404 (RLS, not just UI hide).
- All three Supabase tables have at least one RLS policy and `service_role` is never used
  from the client.
- Lighthouse Best Practices ≥ 95.
