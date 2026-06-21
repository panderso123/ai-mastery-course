# M14 — Project 1: Portfolio site (live in 30 min)

> **Module 14 of 20** · Part 3: Vibe Coding Fundamentals
> **Estimated time:** 60–120 minutes (your first time; ~30 min once you've done it)
> **Outcome:** A live personal website at your own URL with HTTPS.

## Premise

Your first vibe-coded build is a personal portfolio. Low stakes, deployable in under 30 minutes once you know the path, and you end up with something useful. Most importantly: you build the muscle of "prompt → review → ship" on a project where the worst case is ugly fonts.

## Scope — Acceptance test

- Single-page personal site: hero, about, three project cards, contact links.
- Tailwind for styling. No JS framework state. No database.
- Mobile-first. Lighthouse Performance ≥ 95, Accessibility ≥ 95.
- Dark-mode toggle that persists across reloads.
- Deployed to Netlify (or Cloudflare Pages) with HTTPS.

## Walkthrough — Step by step

```bash
# 1. Scaffold
pnpm create next-app@latest portfolio --ts --tailwind --app --eslint --src-dir
cd portfolio

# 2. Drop in your business context
cp ~/AI_Mastery/01_Business_Context/business_context.md ./context/business_context.md
```

3. **Open the agent.** Paste the starter prompt from `04_Code_Projects/portfolio/PROMPT.md` in your Practice Kit. (Reproduced below for reference.)

```text
You are a senior frontend engineer. Build me a single-page personal portfolio
site as a static Next.js (App Router) project with Tailwind. Sections, in order:
  1. Hero — name, one-line value prop, two CTAs.
  2. About — 120-word paragraph + 6 quick-fact bullets.
  3. Selected work — 3 project cards.
  4. Contact — email + 3 social icons. No form.

Visual direction: minimal, lots of whitespace, sans-serif (Inter), single accent
color from the attached business_context.md. Mobile-first. Dark-mode toggle in
the corner. Use only Tailwind utility classes. Prefer one-file simplicity.
```

4. **Agent restates, lists assumptions, writes code.** You review the diff per M13's loop.
5. **Run dev server:** `pnpm dev`. Click around. Have the agent fix anything that looks off.
6. **Push to GitHub.** Connect Netlify (or Cloudflare Pages). Auto-deploy on push.
7. **Add a custom domain** (optional but recommended for the discipline of doing it). Verify HTTPS resolves.

## Exercise — Ship it

- Time-box this to **2 hours.** Shipping is the point. Perfecting is later.
- Commit the design that's "good enough." You'll iterate weekly.
- **Share the URL** in one place where someone might judge it (an industry Slack, a peer DM, your newsletter). Public commitment closes the loop.

**Acceptance test:** Lighthouse Performance ≥ 95, Accessibility ≥ 95, dark-mode toggle persists across reloads, no console errors.

> ✅ **Win pattern.** Ship even if you hate the design. Ugly-and-live beats pretty-and-on-localhost. The site you publish is the site that improves; the site you keep tuning never goes live.

## Knowledge check

1. Why is the portfolio site the right *first* vibe-coded build?
2. What's the lowest acceptable Lighthouse score for the Performance and Accessibility metrics here?
3. Why share the URL in public the same day you ship?

### Answer key

1. Low-stakes. No data, no auth, no payments. The whole project is the practice loop, not the product. If something goes wrong, the worst case is "looks bad."
2. ≥ 95 on both. These thresholds are easily achievable on a static Next.js + Tailwind site; failing them suggests bloat the agent introduced unnecessarily.
3. Public commitment closes the loop. Without it, you'll iterate in private forever. With it, you have an external clock.

## Takeaway

Build #1 is muscle, not portfolio. The portfolio is a happy byproduct. Don't confuse the artifact for the practice.

---

*Previous: [M13 — Development loop](M13_Development_loop.md)* · *Next: [M15 — Project 2: Client dashboard](../04_Building_Real_SaaS/M15_Project2_dashboard.md)*
