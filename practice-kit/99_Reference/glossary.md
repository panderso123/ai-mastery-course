# Glossary

**API** — Application Programming Interface. A defined way for one program to ask another
to do something or return data.

**App Router** — The newer routing system in Next.js where the folder structure under `app/`
defines the URLs.

**Antigravity** — Google's AI-augmented IDE that pairs Gemini with file/terminal tools.

**Business context** — The single document about you and your company that you attach to every
AI run. The "who is asking" side of the prompt.

**Claude Code** — Anthropic's terminal-first coding agent that pairs Claude with file/edit/run
tools.

**CRUD** — Create, Read, Update, Delete. The four operations every database app does.

**Data (in this manual's sense)** — Your historical outputs (tweets, scripts, code) that the AI
learns voice/style from. Not "the database."

**DRY** — Don't Repeat Yourself. If you wrote it twice, refactor it.

**Edge Function** — A small server-side function that runs close to the user. In Supabase, it's
how you do scheduled or webhook work.

**Few-shot** — A prompt that includes 3+ examples of the output you want.

**Hook (content)** — The first 3 seconds (video) or first 2 lines (post) that buy you the rest of
the audience's attention.

**LLM** — Large Language Model. The kind of AI you're prompting (Claude, GPT, Gemini).

**MCP** — Model Context Protocol. A standard for plugging external tools (databases, APIs,
filesystems) into an LLM.

**MVP** — Minimum Viable Product. The smallest version that delivers the core value.

**Prompt** — The instruction you give the model. The "what to do" side of the request.

**Repurposing** — Taking one core idea and shipping it as a long-form, a short-form, a tweet,
and a newsletter.

**RLS (Row-Level Security)** — Postgres feature where the database itself enforces "user A can
only see their own rows." Your last line of defense.

**RSC (React Server Component)** — A component that runs on the server, never ships JS to the
client. The Next.js App Router default.

**SaaS** — Software as a Service. Customers pay (usually monthly) for ongoing access.

**Slop** — Generic, AI-flavored output that anyone could have produced. The thing this manual
exists to prevent.

**Vibe coding** — Building real software primarily by prompting AI rather than typing code,
while still applying engineering judgment about architecture, security, and testing.

**Webhook** — A URL that a third party calls when an event happens (a payment succeeded,
a meeting was scheduled). Always verify the signature.

**Zod** — A TypeScript-first schema validator. Use it at every API boundary.
