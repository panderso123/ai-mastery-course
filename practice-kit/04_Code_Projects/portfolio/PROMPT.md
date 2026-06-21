# Project 1 — Portfolio Site (target: deployed in under 30 minutes)

This project corresponds to **Manual, Chapter 9**.

## What good looks like
- Single-page personal site: hero, about, 3 project cards, contact.
- Tailwind, no JS frameworks, no database.
- Deployed to Netlify with a custom subdomain.

## Starter prompt for Antigravity / Claude Code

> You are a senior frontend engineer. Build me a single-page personal portfolio site as a
> static Next.js (App Router) project with Tailwind. Sections, in order:
>
> 1. Hero — name, one-line value prop, two CTAs (primary "Work with me", secondary "See work").
> 2. About — 120-word paragraph + 6 quick-fact bullets.
> 3. Selected work — 3 project cards (title, 1-line summary, tech tags, link).
> 4. Contact — email + 3 social icons. No form.
>
> Visual direction: minimal, lots of whitespace, sans-serif (Inter), single accent color
> from the attached business_context.md. Mobile-first. Dark-mode toggle in the corner.
> Use only Tailwind utility classes. Prefer one-file simplicity over abstraction.

## Acceptance test (you, manually, in 5 clicks)
1. Page loads in <1.5s on a throttled "Slow 4G" devtools profile.
2. Lighthouse Performance ≥ 95, Accessibility ≥ 95.
3. Dark-mode toggle persists across reloads.
4. Every link works. No console errors.
5. Domain resolves and HTTPS is green.
