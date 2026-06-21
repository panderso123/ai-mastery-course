# Cheat sheet — Prompt engineering, on one page

| Lever | Why it works | Practical move |
|---|---|---|
| **Length** | Long prompts = constrained output. Short prompts = AI guesses. | Aim for 300–800 word prompts for any "real" task. |
| **Role** | Sets evaluation criteria. | "You are an elite [discipline] doing [task] for [audience]." |
| **Process** | Forces step-by-step reasoning before output. | Phase 1 / Phase 2 / Phase 3 sections inside the prompt. |
| **Examples** | Few-shot beats zero-shot every time. | Attach 3–5 of *your* best past outputs. |
| **Constraints** | Negative space defines the result. | "No emoji. No hashtags. No exclamation points." |
| **Format** | Locks output shape so you can compare runs. | "Return JSON with keys X, Y, Z" or "Use this exact template." |
| **Self-critique** | Catches drift in the same call. | End every prompt with: "Then critique your own output in 3 bullets." |
| **Iteration** | The first run is a draft. | Always plan for 2–4 follow-ups; cheap by design. |

## The 1-2-3 rule for sounding like you
1. **One** business context file, attached every time.
2. **Two** dozen of your best past examples (or more).
3. **Three** attempts before you accept any output as "shippable."
