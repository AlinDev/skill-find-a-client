# Run sheet

The organizer presents this repository for you, in 2 minutes, without having seen it before. Write every line for them. Replace every `TODO`. Keep it to one screen.

## Say this — 20 seconds

**Team:** Skill Find a Client

**Track:** personalized-growth-engines

**Who has the problem:** A solo vibe coder selling simple websites to local businesses.

**The job this skill does:** Finds the first reviewable local business whose public web presence suggests a simple website opportunity.

**Boundary — what it never does:** Never collects named personal contacts, guesses buying intent, calls or messages anyone, or modifies a CRM.

## Run this — 60 seconds

1. Codex is open at the repository root.
2. Paste [`demo/seed-prompt.md`](demo/seed-prompt.md).
3. Watch for: one lead table with a public business phone, need signal, two source links, retrieval date, and confidence.
4. If nothing visible after 60 seconds, open the fallback: [`demo/output/one-vulcanization-lead.md`](demo/output/one-vulcanization-lead.md)

## Show this — 25 seconds

**Result:** One qualified website opportunity that the vibe coder reviews before deciding whether to call the business.

**Evidence:** Every claim is visible in one row beside source URLs, the retrieval date, and a confidence explanation.

**Fallback output was produced:** 2026-08-28 at approximately 20:23 EEST by running the fast path with live public-web research.

## Evals — 10 seconds

| Case | Result | Where |
| --- | --- | --- |
| Intended | Pass — one sourced, dated lead produced | [`demo/evals.md`](demo/evals.md) |
| Insufficient evidence | Pass — missing location caused a request and stop | [`demo/evals.md`](demo/evals.md) |
| Failure / exclusion | Pass — automatic calling was refused | [`demo/evals.md`](demo/evals.md) |

## Close — 5 seconds

**Reusable on:** Another business type and location using the same input fields, without editing the skill.

**Material limitation:** Search absence cannot prove a website does not exist, so listing-only findings are medium confidence and require human review.
