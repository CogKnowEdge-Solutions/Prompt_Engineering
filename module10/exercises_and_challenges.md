# Exercises: Before/After Comparison Across Iterations

## Instructions

Work through these with the fictional **TriageBot** task (a ticket classifier returning JSON with `category`, `summary`, `sentiment`) — the same running example from Modules 9 and 10. Each exercise centers on an iteration: a before/after comparison that determines whether a change gets promoted, rejected, or rolled back.

---

## Exercise 1: Before/After — Judge a Change

**v2** made a single change to v1: one few-shot example was added for ambiguous tickets. Score both versions on the same three tickets (rubric: accuracy 0-2, completeness 0-2, clarity 0-1, max 5).

| Ticket | v1 output | v1 score | v2 output | v2 score | verdict (better/same/worse) |
|--------|-----------|----------|-----------|----------|-----------------------------|
| "everything is broken on my account" | v1: `{"category":"general","summary":"User reports general issue.","sentiment":"NEGATIVE"}` | | v2: `{"category":"technical","summary":"User reports full account outage - escalated to engineering.","sentiment":"NEGATIVE"}` | | |
| "is this plan cheaper with a student discount?" | v1: `{"category":"general","summary":"Question about plan price.","sentiment":"NEUTRAL"}` | | v2: `{"category":"billing","summary":"Customer asks about student discount on plan pricing.","sentiment":"NEUTRAL"}` | | |
| "thanks!!" | v1: `{"category":"general","summary":"Customer thanks support.","sentiment":"POSITIVE"}` | | v2: `{"category":"general","summary":"Customer thanks support.","sentiment":"POSITIVE"}` | | |

**Does v2 get promoted (10.6: comparison decides)?** Justify with the scores:
```
[Your answer]
```

---

## Exercise 2: Attribute the Regression

Read the version log below, then answer.

| Version | Change | Why |
|---------|--------|-----|
| v1 | baseline | — |
| v2 | + few-shot example for ambiguous tickets | fix misclassification |
| v3 | reworded the "technical" definition slightly | clarity |
| v4 | removed one few-shot example to shorten prompt | token savings |

After v4 ships, production reports two regressions: (a) ambiguous tickets are misclassified again, and (b) a previously-closed Module 8 injection gap has reopened on tickets that start with an instruction.

**Which version caused (a)? Which likely caused (b)? Why?**
```
[Your answer]
```

**Which of the five properties (10.4) were violated here?**
```
[Your answer]
```

---

## Exercise 3: Write the Hypothesis

For each vague goal, rewrite it as a **specific, falsifiable hypothesis** (10.8, step 1):

| Vague goal | Specific hypothesis |
|------------|---------------------|
| "Make the bot clearer" | |
| "Fix the bad summaries" | |
| "Stop it being hacked" | |
| "It gets too verbose sometimes" | |

**Why does a falsifiable hypothesis matter for the before/after comparison?**
```
[Your answer]
```

---

## Exercise 4: One Change at a Time

A teammate made **two** changes in one version: added an example AND changed the tone instruction. Scores improved 6%.

**Can you attribute the improvement? What should they have done instead?**
```
[Your answer]
```

---

## Exercise 5: Repo vs. Registry Fit

For each team, recommend **prompts-in-the-repo** or **prompts-in-a-registry** (10.3) and give the one reason that tips it:

| Team | Recommendation | Deciding reason |
|------|----------------|-----------------|
| 3 engineers, single product, week-long deploys | | |
| 15 people incl. product managers editing 40 prompts across 5 products, daily releases | | |
| One startup, prompts mostly written by engineers, deploys on demand | | |

**What single property would you demand of a registry before trusting it with a security-sensitive prompt?**
```
[Your answer]
```

---

## Reflection

1. In your before/after tables, was "looks better" ever fighting with "scores better"? Which should win, and why (10.6)?

2. Which of the five properties (10.4) is the first to silently disappear in a small team, and what does losing it cost?

3. For your capstone prompt system, which architecture (10.3) would you ship with — and does it actually deliver all five properties?

---

# Challenge: Build a Personal Iteration Checklist Template

## The Task

Build the reusable checklist you'd actually use for **every** prompt change you make from now on. It must encode the five properties (10.4) and the iteration loop (10.8), and be concrete enough that a teammate could pick it up and follow it without your explanation.

Cover at minimum:

1. **Hypothesis** — where you write the specific, falsifiable claim
2. **Change** — the isolated diff and why one thing
3. **Testing** — both the Module 9 evaluation suite AND the Module 8 adversarial set, with a placeholder for the evaluation scores of old and new versions
4. **Decision gate** — explicit promote / reject / iterate rule based on the comparison
5. **Recording** — version id, change log, and the "why" including rejected attempts
6. **Rollback** — the last known-good version id and how to get back to it

Make it **a template with blanks**, not a description of a template.

---

## My Iteration Checklist Template

```
VERSION:        [e.g. v3]
DATE:           ______
PROMOTING ONTO: [dev / staging / prod]

1. HYPOTHESIS (specific + falsifiable)
   [One line: doing X should change Y by Z]

2. THE CHANGE (one isolated difference)
   Diff vs previous version:
   ____________
   Why only this change: ____________

3. TESTING
   Eval suite (Module 9):   previous __ / new __   (rubric avg)
   Sanity checks:           previous __ / new __
   Adversarial set (M8):    previous __ / new __   (gaps held? __)

4. DECISION GATE (based on comparison, not intuition)
   [ ] Promote to next environment    why: ____________
   [ ] Reject                         why: ____________
   [ ] Iterate again (go back to 2)   why: ____________

5. RECORD
   Version id: __________
   Change log line: __________
   Why (including ANY rejected attempt): __________

6. ROLLBACK PLAN
   Last known-good version id: __________
   Command / action to restore: __________
```

---

## Evaluation Criteria

| Criteria | Points |
|----------|--------|
| Hypothesis field requires a specific, falsifiable claim | 15 |
| Change field enforces one isolated change | 15 |
| Testing covers Module 9 suite AND Module 8 adversarial set | 20 |
| Decision gate is based on comparison, not vibes | 15 |
| Recording includes rejected attempts and the why | 15 |
| Rollback plan names a specific version id | 10 |
| Template is fill-in-the-blank usable (not just prose) | 10 |
| **Total** | **100** |

---

## Bonus Challenge

Use your template on one NOTIONAL change (pick any change to TriageBot, fill every field, and state whether it would pass your own gate). This is the first real use of the template — fix any blanks you can't fill.

```
[Your filled template run]
```