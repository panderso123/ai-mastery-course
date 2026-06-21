# M12 — How web apps actually work

> **Module 12 of 20** · Part 3: Vibe Coding Fundamentals
> **Estimated time:** 60 minutes
> **Outcome:** You can sketch any feature in 90 seconds as the four-line spec the agent needs to build it.

## Premise

You don't need computer science to vibe-code well. You need a **working mental model** of how the parts fit together so that when the agent goes off the rails you know which lever to pull. This module installs that model.

## Concept — The five-layer model

| Layer | What it does | Examples |
|-------|--------------|----------|
| **Frontend** | What the user sees. Buttons, forms, animations. | Next.js pages, React components, Tailwind. |
| **API / backend** | Server-side logic. Validates input, talks to DB and third parties. | Next.js Route Handlers, Express endpoints. |
| **Database** | Where data lives between visits. | Postgres (via Supabase), MongoDB. |
| **Auth** | Who is making the request, and what are they allowed to do. | Supabase Auth, Clerk, NextAuth. |
| **Hosting / infra** | Where the code runs in production. | Netlify, Vercel, Cloudflare Pages. |

Every "feature" you build threads through some subset of these layers.

## Concept — Every feature is a CRUD verb

Almost every feature in almost every app is one of four verbs against a piece of data:

- **Create** — a new row appears (signup, post a comment, add an article).
- **Read** — existing rows are fetched (your dashboard, an article page).
- **Update** — a row's fields change (edit profile, mark as approved).
- **Delete** — a row goes away (remove a teammate, cancel a draft).

Once you see this pattern, you can sketch any feature as: *"which verb, on which table, by which user, with what permission?"* That sentence is exactly the prompt the agent needs.

## Walkthrough — Thinking out a feature in 90 seconds

**Feature:** "Clients should be able to leave a note on an article and the writer should see it in real time."

Sketch:

1. **Verb:** Create.
2. **Table:** `notes(id, article_id, author_user_id, body, created_at)`.
3. **Who:** any user whose `user_id` has access to the parent article (RLS policy).
4. **Side effect:** broadcast to the writer's open dashboard via a Supabase realtime channel.

That four-line sketch becomes the prompt. The agent does the typing.

## Exercise — Sketch three features

Take three features from any product you use daily. (Examples: "I can react to a Slack message with an emoji," "I can save a Spotify song to my library," "I can DM another LinkedIn user.") For each, write the four-line sketch:

```text
Verb:
Table(s):
Who:
Side effect:
```

You'll use this skill in every coding chapter from here on.

**Acceptance test:** all three sketches fit on one screen and you can read each one out loud without stumbling.

> ✅ **Win pattern.** This four-line sketch is the difference between vibe-coders who ship and those who chase the agent in circles. If you can't write it in 90 seconds, the feature is too big — split it.

## Knowledge check

1. Name the five layers of the web app model.
2. What four CRUD verbs cover most features?
3. What's the role of the four-line sketch in the vibe-coding workflow?

### Answer key

1. Frontend, API/backend, database, auth, hosting/infra.
2. Create, Read, Update, Delete.
3. It compresses the feature into the minimum information the agent needs to build it correctly. Skipping the sketch lets the agent invent assumptions, which produces drift you'll only notice in production.

## Takeaway

You're never going to memorize how every part of a web app works. You don't need to. Memorize the five layers and the four verbs. Sketch features in those terms. The agent does the rest.

---

*Previous: [M11 — Setup](M11_Setup.md)* · *Next: [M13 — The vibe-coding development loop](M13_Development_loop.md)*
