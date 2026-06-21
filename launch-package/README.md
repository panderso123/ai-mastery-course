# Course Launch Package — Read this first

This folder is everything you need to launch **AI Mastery: From Slop to Shipped**
as a paid course with a free lead-magnet funnel feeding it. Built on top of the
56-page Practice Manual and Practice Kit that already live one folder up.

## What's in the box

```
Course_Launch_Package/
├── README.md                          ← you are here
├── STRATEGY.md                        ← the funnel + tier breakdown
│
├── 01_Lead_Magnet/                    ← the free 10-page PDF
│    ├── AI_Mastery_Starter_Guide.docx
│    └── AI_Mastery_Starter_Guide.pdf  ← attach this to email 0
│
├── 02_Landing_Page/                   ← single-file landing page
│    └── index.html                    ← deploy to Netlify; point a domain at it
│
├── 03_Email_Sequence/                 ← 5-email nurture, ready to import
│    ├── README.md                     ← variables to find-and-replace
│    ├── 00_day0_deliver.md            (instant)
│    ├── 01_day2_value.md              (+2d)
│    ├── 02_day4_case.md               (+4d)
│    ├── 03_day6_softpitch.md          (+6d)
│    └── 04_day9_hardpitch.md          (+9d)
│
├── 04_Curriculum_and_Pricing/         ← public-facing syllabus + tiers
│    ├── Course_Syllabus.docx
│    └── Course_Syllabus.pdf
│
└── 05_Sales_Assets/                   ← reusable copy snippets
     ├── headlines.md                  ← page heroes, CTAs
     ├── tweet_threads.md              ← 3 pre-launch threads
     └── ad_copy.md                    ← Meta, Google, Reddit
```

Plus, sitting one folder up:

```
../AI_Mastery_Practice_Manual.docx     ← the 56-page paid product
../AI_Mastery_Practice_Manual.pdf
../AI_Mastery_Practice_Kit/            ← the drop-in Practice Kit
```

## A 60-minute "go-live" checklist

If you wanted to launch literally today, this is the path.

1. **Buy a domain** on Cloudflare or Porkbun (~$12/year). Anything you like —
   `aimastery.com`, `slop-to-shipped.com`, `[yourname].ai`.
2. **Create a Netlify account.** Drop `02_Landing_Page/index.html` into
   `netlify.com/drop`. Point your domain at the resulting URL. Done — your
   landing page is live with HTTPS in 5 minutes.
3. **Create a Resend (or MailerLite / ConvertKit) account.** Verify your sending
   domain (SPF + DKIM via your DNS).
4. **Import the email sequence.** Each `.md` file is frontmatter + body — every
   modern ESP imports this format. Set the delays to match the frontmatter
   `delay_minutes`. Trigger: contact added to list `ai-mastery-leadmagnet`.
5. **Wire the opt-in.** Replace the `submitOptin` JS in `index.html` with a real
   POST to your ESP's form endpoint. Resend's API takes 4 lines.
6. **Upload the lead magnet.** Host `AI_Mastery_Starter_Guide.pdf` on Netlify (or
   anywhere with a stable URL). Update the link in `00_day0_deliver.md` to point
   at it.
7. **Find-and-replace placeholders** across the package:
   - `aimastery.example.com` → your real domain
   - `hi@aimastery.example.com` → your real from address
   - `{{first_name}}` and `{{sender_name}}` → your ESP's syntax
   - `STARTER25` → your real promo code (or remove)
   - `Aman` and `$4,200` in `02_day4_case.md` → a real student/testimonial,
     or **remove the case study entirely** if you don't have one (do not
     fabricate)
8. **Set up checkout.** Stripe Payment Links for Starter ($79) and Pro ($249).
   Cohort goes through an application form (Tally / Typeform) for the first
   few cohorts.
9. **Test the funnel end-to-end** with a fresh email address. Opt in. Read every
   email on mobile and desktop. Click every link. Buy your own product. Refund
   yourself.
10. **Launch.** Day 1 of the 21-day playbook in `STRATEGY.md`. Post Tweet
    Thread 1 from `05_Sales_Assets/tweet_threads.md`.

## What this package will not do for you

- **It will not write a real testimonial.** Replace placeholder student names
  and numbers before going live. The penalty for making one up is worse than
  the upside of having one.
- **It will not buy traffic.** The launch playbook assumes you have ~50–500
  warm contacts somewhere (newsletter, Twitter, LinkedIn) to seed the first
  wave. Cold ads should come *after* the first cohort sells out.
- **It will not maintain itself.** Refresh the manual every quarter, update the
  email-series links, refresh the landing page testimonials. Stale launch
  packages convert worse than honest ones.

## The honest version of this README

Most "course launch packages" you'll find online assume you have nothing real
underneath them — the funnel exists to sell air. This one assumes you have
the actual 56-page Practice Manual and Practice Kit in the parent folder,
because *those are the product*. The funnel exists to put the product in
front of people who would benefit from it.

If those two assets aren't excellent — if you haven't read the manual, used
the Kit, and felt the system click yourself — the funnel will sell, and your
first cohort will refund. Read the manual first. Then launch.

— Built using exactly the workflow the course teaches.
