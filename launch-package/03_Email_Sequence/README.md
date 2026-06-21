# Email Nurture Sequence — README

A 5-email sequence that runs on opt-in to the lead magnet. Designed for any
modern ESP (Resend, MailerLite, ConvertKit, Beehiiv, Substack — all import
markdown with frontmatter).

## The cadence

| # | File | Day | Job |
|---|---|---|---|
| 0 | `00_day0_deliver.md` | 0 (instant) | Deliver the PDF + set the cadence |
| 1 | `01_day2_value.md` | +2 days | Pure value: the prompt-length law + production prompt |
| 2 | `02_day4_case.md` | +4 days | Case study: real student, real numbers |
| 3 | `03_day6_softpitch.md` | +6 days | Introduce the product + STARTER25 code |
| 4 | `04_day9_hardpitch.md` | +9 days | Last-call urgency, honest direct ask |

## How to use

1. **Set up automation.** In your ESP, create a list `ai-mastery-leadmagnet` and an
   automation triggered by adding a contact to that list.
2. **Map the delays.** Each email's `delay_minutes` frontmatter is the offset from
   the trigger. (0 / 2880 / 5760 / 8640 / 12960.)
3. **Configure merge tags.** Replace `{{first_name}}` and `{{sender_name}}` with
   your ESP's syntax.
4. **Set the from address.** Update `from_email` and verify the sending domain.
5. **Test.** Send all 5 to yourself first. Read on mobile.

## Variables to find-and-replace before going live

- `{{first_name}}` — first name merge tag
- `{{sender_name}}` — your name (e.g., "Peter")
- `aimastery.example.com` — your real domain
- `hi@aimastery.example.com` — your real from address
- `STARTER25` — your real promo code (or remove if not running one)

## Compliance notes

- Every email needs a one-click unsubscribe link (most ESPs add this automatically).
- The from address must match a verified sending domain (SPF + DKIM + DMARC).
- Day 4's case study mentions specific numbers — replace "Aman" and the dollar
  figure with your own real student or testimonial. Do not ship a fabricated case
  study; CAN-SPAM and ASA rules treat that as deceptive.

## What this sequence is NOT optimized for

- B2B enterprise sales cycles (those need a 14–30 email sequence with more proof).
- Free-trial-to-paid conversion (different motion entirely; use a separate trial
  drip).
- Webinar or live launch sequences (those are 10+ emails over 2 weeks with
  countdown timers).

This is a **lead-magnet → low-ticket digital product** sequence, optimized for the
"impulse-considered-purchase" tier ($79–$999 one-time).
