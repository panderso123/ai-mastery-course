# Import this curriculum into Notion

This folder is structured so Notion's markdown import recreates the page tree
exactly as designed. ~5 minutes end to end.

## Step 1 — Zip the folder

In Finder, right-click the `Curriculum_for_Notion` folder and choose **Compress**.
You'll get `Curriculum_for_Notion.zip`.

## Step 2 — Import in Notion

1. Open Notion. Pick the workspace where you want the course to live.
2. In the sidebar, click **+ Add new page** (or use an existing parent page like "Courses").
3. Inside the new blank page, click the `…` menu (top-right) → **Import** → **Markdown & CSV**.
4. Select `Curriculum_for_Notion.zip`.
5. Wait ~30 seconds. You'll get a page tree like:

```
AI Mastery — Course Curriculum   ← README.md
├── Import to Notion              ← IMPORT_TO_NOTION.md
├── 01 Foundation                 ← folder = sub-page
│   ├── README                    ← Part overview
│   ├── M01 The slop problem
│   ├── M02 The 4-folder system
│   └── ...
├── 02 Content Workflows
└── ...
```

## Step 3 — Cosmetic cleanup (10 minutes)

After import, do these to make it feel native:

- **Rename the top page.** Click "AI Mastery — Course Curriculum" and call it whatever your students will see ("AI Mastery 1.0", "Slop to Shipped Cohort 2", etc.).
- **Promote the Part folders.** Each `01_Foundation/README.md` becomes a sub-page called "README." You can either delete that README and rename the parent, or use it as the part overview (it already has overview content).
- **Convert "Answer key" sections to toggles.** In each module:
   1. Find the `### Answer key` heading near the bottom.
   2. Hover the line → click the `⋮⋮` handle → **Turn into → Toggle heading 3**.
   3. The answers now hide by default. Students self-test, then click to reveal.
- **Add a cover image** to the top page (Notion suggestion: an unsplash gradient in your accent blue).
- **Set page icons** on each Part (1️⃣ 2️⃣ 3️⃣ 4️⃣ 5️⃣ work fine).

## Step 4 — Optional: turn it into a sellable course

If you want to actually sell access (rather than just share Notion pages):

| Need | Tool | Why |
|------|------|-----|
| Sell access to a Notion page | **Super.so** or **Whalesync + Memberstack** | Wraps your Notion site with auth + Stripe. Cheapest path to a paid course. |
| Real LMS (lessons, completions, certificates) | **Teachable** or **Podia** | Import the same .md files; gives quizzes, progress, certificates. |
| Self-host with full control | **Outline** or static site (Astro + Markdown) | All these `.md` files drop in directly. |

Notion is fine for cohort-style delivery (you share the parent page with the cohort). For mass self-paced sale, move to Teachable or Podia after your first 1–2 cohorts validate the offer.

## Pitfalls

- **Don't unzip first then drag the folder in.** Notion's import expects the zip.
- **Don't import individual `.md` files one at a time.** You lose the parent/child structure.
- **Tables look fine in import.** Notion handles markdown tables out of the box.
- **Code blocks preserve their language.** ` ```bash`, ` ```ts`, ` ```sql` all survive.
- **Internal links between modules don't auto-fix.** After import you'll see literal `[M02 — ...](M02_...md)` text. Notion 2.0 fixes some of these on import; otherwise, do a once-over and click the broken-link fixer Notion offers in the right sidebar.

## You're done.

Share the parent page with edit access (for cohort) or read access (for self-paced students). Done.
