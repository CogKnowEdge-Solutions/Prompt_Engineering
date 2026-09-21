# Lab: Take One Prompt Through 3 Iterations

## Objective

Apply the full Module 10 iteration loop: take a single prompt through three versioned iterations, each driven by a specific hypothesis, measured with the Module 9 evaluation suite and the Module 8 adversarial set, comparing every change to the previous version and recording what changed and why.

## The Starting Prompt (v1)

Continuing the fictional **TriageBot** task from Module 9 — classifies a support ticket and returns JSON. This is **v1**.

```
v1:
Classify the support ticket as technical, billing, or general.
Return JSON with category, summary (one sentence), and
sentiment (POSITIVE, NEUTRAL, or NEGATIVE).
Ticket: {{TICKET}}
```

**The known pain:** ambiguous tickets get misclassified ("everything is broken on my account" is classified `general` when it's really `technical`).

---

## Iteration 1: v1 → v2

**1. Your hypothesis (specific, from 10.8 — not "make it better"):**
```
[Adding a few-shot example of an ambiguous ticket should push the model toward
the right category on those cases.]
```
*(Write your own — be specific.)*

**2. Your one change (flush in the version diff below):**
```
[v2 prompt - paste the full new prompt]
```

**What changed vs v1, and why only this one thing:**
```
[Change description]
```

**3. Before/After comparison table** (run v1 and v2 on the same 10 tickets, score with the Module 9 rubric: accuracy/completeness/clarity, 0-5):

| Ticket | v1 score | v2 score | Adversarial set result (v1) | Adversarial set result (v2) |
|--------|----------|----------|-----------------------------|-----------------------------|
| 1 | | | | |
| 2 | | | | |
| ... to 10 | | | | |
| **Average** | | | | |

**4. Decision (promote / reject / iterate again — with 10.6's evidence):**
```
[Your decision + the score evidence]
```

**5. Record what changed and why (6th step of the loop):**
```
[Version log entry for v2]
```

---

## Iteration 2: v2 → v3

**1. Your hypothesis (specific):**
```
[New hypothesis - e.g., an instruction to use general when there's not enough
information should stop confident invention on no-answer tickets]
```

**2. Your one change (flush the version diff below):**
```
[v3 prompt - paste the full new prompt]
```

**What changed vs v2, and why only this one thing:**
```
[Change description]
```

**3. Before/After comparison** (same 10 tickets, plus your adversarial set):

| Ticket | v2 score | v3 score | Adversarial set result (v2) | Adversarial set result (v3) |
|--------|----------|----------|-----------------------------|-----------------------------|
| 1 | | | | |
| ... to 10 | | | | |
| **Average** | | | | |

**Did a Module 8 gap reopen in v3 (10.7)?** Run the adversarial set and check explicitly:
```
[Yes/No + which category reopened, if any]
```

**4. Decision with evidence:**
```
[Your decision + score evidence]
```

**5. Record:**
```
[Version log entry for v3]
```

---

## Iteration 3: v3 → v4 (Worst Case, Roll Back)

This time the hypothesis is wrong. Purposefully make a change you **expect** to fail on one dimension (e.g., remove the few-shot example to shorten the prompt), then run the loop anyway — and roll back using 10.2's immutable version artfact.

**1. Hypothesis (a deliberately risky one):**
```
[Your risky hypothesis]
```

**2. The change you make (v4):**
```
[v4 prompt - paste it]
```

**3. Before/After comparison:**

| Metric | v3 | v4 | Pass? |
|--------|-----|-----|-------|
| Rubric average (/5) | | | |
| Sanity checks (all 10 pass JSON?) | | | |
| Adversarial set fully held? | | | |

**4. Decision — and if v4 failed, the rollback:** revert to the last known-good version; state which version id that is.
```
[Decision + rollback target version id]
```

**5. Record the failed attempt** so no one re-tries it:
```
[Version log entry for v4 - including WHY it failed]
```

---

## Final Version Log

| Version | Change (one line) | Why | Eval avg | Adversarial held? | Decision |
|---------|-------------------|-----|----------|--------------------|----------|
| v1 | — baseline | — | | | |
| v2 | | | | | |
| v3 | | | | | |
| v4 | | | | | |

**Which single winning version would you deploy to staging next, and why (10.5)?**
```
[Your answer]
```

---

## Discussion Questions

1. In Iteration 1, could you attribute the score change to your hypothesis even if it improved? What would have made attribution impossible?

2. Where did the adversarial set catch something that simple rubric scoring did not?

3. If these prompts lived in a chat tool with no versioning, which version would you "have been running" this whole time?

4. Would prompts-in-the-repo or prompts-in-a-registry (10.3) have made this lab easier or harder, and why?

---

## Key Takeaways

Fill in your observations:

- Best single iteration this lab: _______________
- The fix I most often needed to make a hypothesis falsifiable: _______________
- My winning version id and its one-line change: _______________
- What I'd version next time BEFORE starting to edit: _______________