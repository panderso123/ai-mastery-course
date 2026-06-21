# M13 — The vibe-coding development loop

> **Module 13 of 20** · Part 3: Vibe Coding Fundamentals
> **Estimated time:** 45 minutes
> **Outcome:** You can ship a clean change end-to-end without skipping the diff review or the manual test.

## Premise

Vibe coding has a different rhythm from traditional coding. You spend more time framing the problem and reviewing the diff, less time typing. The discipline of the loop is what separates ten useful projects from one tangled mess.

## Concept — The six-step loop

1. **Plan** the change in plain English. (Use Practice Kit `03_Prompts/06_idea_to_spec.md` for any change bigger than a button.)
2. Have the agent **restate the plan** and list the files it will touch. *Do not skip this.*
3. **Approve.** Agent writes code.
4. **Read the diff.** Don't accept blind. Watch for fabricated APIs, mis-named columns, or missing types.
5. Run the **manual test list** the agent provides.
6. **Commit.** (`git commit -m` messages should describe the change, not the prompt.)

> 💡 **Key idea.** Treat the agent like a smart junior engineer who is fast, eager, and occasionally wrong with confidence. Your job is the architect / reviewer role — scope, sequence, sanity-check.

## Walkthrough — A clean change

**Goal:** add a "Mark all as read" button to the notes panel.

```text
1. PROMPT (you to agent):
   "Read components/NotesPanel.tsx. Add a 'Mark all as read' button at the top right
    of the panel. It should call /api/notes/mark-all-read which sets read_at = now()
    on every note for the current user in the current article. Use Zod to validate
    the body. Return updated count.
    DO NOT WRITE CODE YET — first restate the change, list the files you'll touch,
    list assumptions."

2. AGENT (in chat):
   "Plan: add a button + a route. Files I'll touch:
     - components/NotesPanel.tsx (button + handler)
     - app/api/notes/mark-all-read/route.ts (new)
     - lib/db.ts (new query function)
   Assumptions:
     - notes table has a read_at timestamp column
     - the current user is identified via Supabase auth
   Confirm or correct."

3. YOU:
   "Confirmed."

4. AGENT writes code. You READ THE DIFF.
   - Button appears in correct place: ✓
   - Route handler validates input with Zod: ✓
   - New db function uses parameterized query: ✓
   - tsc --noEmit passes: ✓

5. YOU click the button. Notes update. Console clean. Network tab clean.

6. git commit -m "feat(notes): mark all as read button"
```

Every step. Every time. The discipline is what makes the agent productive over months.

## Exercise — Run the loop on a tiny change

Pick a tiny change to your portfolio site (M14 will be the first project — for now use any sample repo, or your future portfolio). Examples:

- "Add a copy-email-to-clipboard button next to my email link."
- "Add a 'last updated' line in the footer."
- "Add a keyboard shortcut to toggle dark mode."

Run the full 6-step loop. Don't skip restate. Don't skip diff review. Don't skip manual test.

**Acceptance test:** you can describe in one sentence each what the agent did between steps 3 and 4 — and what you found in the diff at step 4.

> ⚠️ **Pitfall.** Skipping the diff review *feels* fast in week one. By week three, the agent has silently introduced duplicate database connections, stray `any` types, or imports that don't exist. Read every diff. It takes 60 seconds and saves 60 hours.

## Knowledge check

1. What's the purpose of having the agent restate the plan before writing code?
2. Why is the diff review the most important step in the loop?
3. What's the right relationship between you and the agent?

### Answer key

1. It surfaces assumptions before the agent commits to wrong ones. Catching a wrong assumption before code is written is dramatically cheaper than after.
2. It's where you catch fabricated APIs, wrong column names, missed types, and architectural drift. The agent will *confidently* produce wrong code; the diff is the only place you see it before it's running.
3. Architect / reviewer ↔ smart junior pair. You scope and sequence; the agent types. You catch errors; the agent fixes them. Don't delegate architecture; don't try to type faster than the agent.

## Takeaway

The loop is the product. Without the loop, you have a chatbot that writes code. With the loop, you have a development practice that ships maintainable software at 5x the pace.

---

*Previous: [M12 — How web apps actually work](M12_How_web_apps_work.md)* · *Next: [M14 — Project 1: Portfolio site](M14_Project1_portfolio.md)*
