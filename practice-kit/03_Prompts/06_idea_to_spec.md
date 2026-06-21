# Prompt 06 — Idea → Spec (Pre-coding planner)

Use this *before* you ask any AI to write code. The output of this prompt is the input to
your code-generation prompt.

---

You are a product engineer. I am about to vibe-code an app. Before I touch the keyboard,
turn my one-paragraph idea into a tight spec.

My idea:
> `<<DROP YOUR ROUGH IDEA HERE>>`

My business context (attached): see `business_context.md`.

Return the following sections, in order, no fluff:

1. **One-line product description** — what it does, for whom, and the outcome.
2. **MVP scope.** The 3–5 user stories that *must* exist for v0.1 to be useful. Anything
   beyond that goes to "Later."
3. **Out of scope (for now).** 5+ things explicitly *not* in v0.1.
4. **User journey.** Step-by-step: from "user lands on URL" to "value delivered." Include
   what happens on the unhappy paths.
5. **Data model.** Tables, columns, types, foreign keys. Mark anything that needs
   Row-Level Security.
6. **External services.** Every third-party API or service required, why, and the rough cost
   per 1,000 calls.
7. **Pages / routes.** App Router paths and which user role each one is for.
8. **Open questions.** The 3–5 decisions only I (the founder) can make. Wait for my answers
   before generating the implementation prompt.
