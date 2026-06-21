# Cheat sheet — The default vibe-coding stack

| Layer | Choice | Why this and not X |
|---|---|---|
| Language | TypeScript | Saves you from a class of bugs the model won't catch on its own. |
| Framework | Next.js (App Router) | One repo for frontend + API routes. Vercel/Netlify deploy in one click. |
| Styling | Tailwind CSS | The model writes Tailwind better than it writes CSS modules. |
| UI primitives | shadcn/ui | Copy-paste components. You own the code, not a black box. |
| DB + Auth | Supabase | Postgres + Auth + Row-Level Security + real-time channels in one box. |
| Hosting | Netlify (or Vercel) | Free tier covers MVP. Deploy on git push. |
| Payments | Stripe | Webhook-driven. Treat the dashboard as the source of truth, not the client redirect. |
| Email | Resend | Cleanest API, generous free tier. |
| Background jobs | Postgres queue + Supabase Edge Functions on cron | No Redis, no extra service. |
| Error monitoring | Sentry (free) | Set it up on day 1, not after the first outage. |

## Files you should always have on day 1
```
.env.example          # documented, not real values
.gitignore            # ignores .env*, .next, node_modules
README.md             # 1 paragraph "what is this", 1 paragraph "how to run"
supabase/migrations/  # every schema change committed
lib/db.ts             # the only place that imports the Supabase server client
lib/auth.ts           # the only place session state is read on the server
```
