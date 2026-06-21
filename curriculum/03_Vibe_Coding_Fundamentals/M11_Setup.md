# M11 — Setup: Claude Code or Antigravity

> **Module 11 of 20** · Part 3: Vibe Coding Fundamentals
> **Estimated time:** 30 minutes
> **Outcome:** A working coding environment with the agent installed, authenticated, and obeying your house rules.

## Premise

Vibe coding requires a setup that makes prompting first-class. Two tools dominate the category in 2026: **Claude Code** (Anthropic's CLI agent) and **Antigravity** (Google's AI-first IDE). Either works; the workflow is the same. Cursor, Windsurf, and Zed are all viable too — same patterns apply.

## Concept — Choosing your stack

| Tool | Best for | Notes |
|------|----------|-------|
| **Claude Code** | Terminal-first builders, anyone who lives in a shell. | Pairs with any IDE you like; runs commands, edits files, reads docs. |
| **Antigravity** | Visual IDE preference, want a built-in agent panel. | Bundles file explorer, editor, chat panel, Gemini access. |
| Cursor / Windsurf / Zed | VS Code refugees who want inline AI. | Same workflow patterns apply. |

> 💡 **Key idea.** The choice matters less than the discipline. Whichever tool you pick, paste in `04_vibe_coding_rules.md` (from your Practice Kit's `03_Prompts/`) as a permanent rule so the agent inherits your house style on day one.

## Walkthrough — Bringing up a clean environment

```bash
# 1. Node 20 LTS + pnpm
brew install node@20 pnpm   # or fnm, or volta — whatever you use

# 2. Install your agent
npm i -g @anthropic-ai/claude-code   # OR download Antigravity from antigravity.google

# 3. Authenticate
claude login                          # OR sign in to Antigravity with Google

# 4. Project root
mkdir my-first-vibe && cd $_ && git init

# 5. Drop in your AI Mastery folder so business context is one prompt away
cp -r ~/AI_Mastery .

# 6. Open the agent panel; paste 04_vibe_coding_rules.md as a global / project rule

# 7. Sanity-check prompt
# Ask the agent: "Create hello.txt with the current date."
# Verify the file appears in your project.
```

## Exercise — Prove your environment works

1. Complete steps 1–7 above.
2. Ask the agent: *"Read my `business_context.md`. Then summarize who I am in three sentences."*
3. If the summary sounds like you, you're wired up correctly.
4. If the summary sounds generic, your `business_context.md` is too thin — go back to **M3** before continuing.

**Acceptance test:** the agent can read your business context AND edit a file in your project root.

> ⚠️ **Pitfall.** Don't skip pasting in the house rules. Without them, every new chat with the agent starts from defaults — you lose the architectural standards you set last week and your codebase drifts within days.

## Knowledge check

1. What's the role of `04_vibe_coding_rules.md` in this setup?
2. Why install Node 20 LTS rather than the latest version?
3. If the agent's summary of your business context sounds generic, what should you fix?

### Answer key

1. It's a global rule the agent reads at the start of every session. It encodes your stack defaults, security defaults, and process defaults so the agent doesn't have to re-derive them every time.
2. LTS means Long-Term Support: a stable version with security patches that's compatible with virtually every library you'll touch. Latest can break ecosystem packages.
3. The business context file. The agent is just reading what you wrote. Generic in → generic out. Re-do M3.

## Takeaway

Setup is one afternoon and never again. Skipping the rules file is the single most common cause of "the agent doesn't get my project anymore" three weeks later.

---

*Previous: [M10 — Content rhythm](../02_Content_Workflows/M10_Content_rhythm.md)* · *Next: [M12 — How web apps actually work](M12_How_web_apps_work.md)*
