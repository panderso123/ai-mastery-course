# Course Launch Package — Strategy

## The product

**AI Mastery: From Slop to Shipped.**
A self-paced course (with optional cohort tier) that takes a non-technical operator
from "AI sounds generic when I prompt it" to "I have a deployed SaaS app and I
publish on-voice content every week."

Built from the synthesis of two source curriculums (content workflow + vibe coding)
and packaged as the AI Mastery Practice Manual + Practice Kit, plus video and
community layers for the higher tiers.

## The funnel

```
                ┌──────────────────────────────────────┐
                │  Cold traffic                         │
                │  (X, LinkedIn, YouTube, podcasts)     │
                └─────────────────┬────────────────────┘
                                  ▼
              ┌────────────────────────────────────────┐
              │  LANDING PAGE                          │
              │  Headline: stop sounding like ChatGPT  │
              │  Single CTA: get the free starter PDF  │
              └─────────────────┬─────────────────────┘
                                ▼
              ┌────────────────────────────────────────┐
              │  EMAIL CAPTURE → LEAD MAGNET           │
              │  "The 4-Folder System" (15-page PDF)   │
              └─────────────────┬─────────────────────┘
                                ▼
              ┌────────────────────────────────────────┐
              │  5-EMAIL NURTURE SEQUENCE              │
              │  Day 0 deliver → Day 2 value           │
              │  Day 4 case  → Day 6 soft pitch        │
              │  Day 9 hard pitch                      │
              └─────────────────┬─────────────────────┘
                                ▼
              ┌────────────────────────────────────────┐
              │  SALES PAGE → CHECKOUT                 │
              │  Tiers: Starter / Pro / Cohort         │
              └────────────────────────────────────────┘
```

## The three tiers

| Tier | Price | Who it's for | What's inside |
|---|---|---|---|
| **Starter** | $79 one-time | Operators who want the playbook | 56-page Practice Manual (PDF + DOCX) • Practice Kit folder • 6 prompt templates • Lifetime updates |
| **Pro** | $249 one-time | Builders who want to ship | Everything in Starter • 3 starter code repos (portfolio, dashboard, lead-gen SaaS) • 8 video walkthroughs • Private community Discord |
| **Cohort** | $999 (cap 25/cohort) | Founders ready to launch | Everything in Pro • 4-week live cohort • 4 weekly group office hours • 1 hot-seat review • Certificate |

## Positioning

- **Promise:** "In 30 days, you will publish content that sounds like you and ship a real SaaS app — using nothing but AI you already know how to talk to."
- **Mechanism:** The 4-folder system (business context + data + prompts + projects).
- **Proof:** A 56-page manual built on synthesized real-world workflows; 3 working starter repos; opinionated guardrails honed from production builds.
- **Differentiator:** Most AI courses teach prompts. This one teaches the *system around* the prompts so output quality compounds over time.

## Launch sequence (21 days)

1. **Days -21 to -7** — pre-launch list. Drive 200+ emails via lead magnet.
2. **Days -6 to -1** — soft launch to email list (early-bird $20 off).
3. **Day 0** — public launch on X / LinkedIn / Product Hunt.
4. **Days 1–7** — daily content during launch week, social proof, FAQs.
5. **Days 8–14** — last-call urgency, bonus expiry, cohort cap reminder.
6. **Day 21** — after-action report; iterate offer; restart cycle.

## Files in this package

```
Course_Launch_Package/
├── 01_Lead_Magnet/                 # Free PDF + the docx-js source
│    ├── AI_Mastery_Starter_Guide.docx
│    └── AI_Mastery_Starter_Guide.pdf
├── 02_Landing_Page/                # Single-file landing page
│    └── index.html
├── 03_Email_Sequence/              # 5 emails ready to paste into Resend/Mailchimp
│    ├── 00_day0_deliver.md
│    ├── 01_day2_value.md
│    ├── 02_day4_case.md
│    ├── 03_day6_softpitch.md
│    └── 04_day9_hardpitch.md
├── 04_Curriculum_and_Pricing/      # Public-facing syllabus + pricing one-pager
│    ├── Course_Syllabus.docx
│    └── Course_Syllabus.pdf
├── 05_Sales_Assets/                # Reusable copy snippets for socials/ads
│    ├── headlines.md
│    ├── tweet_threads.md
│    └── ad_copy.md
└── STRATEGY.md                     # This document
```

## What's intentionally NOT included

- Stripe checkout integration code. Use Stripe Payment Links — no code required.
- Video files. The video walkthroughs are out of scope for a doc package; placeholders link to where they would go (Loom / Wistia).
- Email-sending infrastructure. Plug the email sequence into Resend, MailerLite, or ConvertKit — they all import Markdown.
- A custom domain. Buy one ($12/yr); point it at Netlify; deploy index.html. 5 minutes.
