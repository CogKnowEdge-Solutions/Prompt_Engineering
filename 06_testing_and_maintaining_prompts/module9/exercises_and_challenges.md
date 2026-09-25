# Exercises: Rubric Scoring & Eval Design

## Instructions

Work against the fictional **TriageBot** scenario used across this module's lab: a support system that reads a support ticket and outputs a JSON record with `category`, `summary` (one sentence), and `sentiment` (`POSITIVE` / `NEUTRAL` / `NEGATIVE`). Evaluation content stays fictional throughout.

---

## Exercise 1: Sanity vs. Quality — Classify the Check

For each check below, mark whether it's a **sanity check** (fast, deterministic, unit-test-style) or **quality evaluation** (judgment-based, expensive).

| # | Check | Sanity or Quality? |
|---|-------|--------------------|
| 1 | Output parses with `json.loads()` | |
| 2 | `category` is one of the three allowed values | |
| 3 | The one-sentence summary is actually an accurate digest of the ticket | |
| 4 | `summary` length is under 200 characters | |
| 5 | A `sentiment` field exists | |
| 6 | The response reads like a human wrote it, not a template | |
| 7 | The category matches what a domain expert would pick | |

**Why does the order matter (sanity first)?**
```
[Your answer]
```

**Check your work:**
- [ ] All 7 rows are classified (sanity or quality)
- [ ] The judgment-based rows (summary accuracy, human-like readability, expert category match) are marked as quality
- [ ] "Why the order matters" notes that sanity checks are cheap, deterministic, and gate the expensive judgment steps

---

## Exercise 2: Rubric Scoring

Score each TriageBot output against this rubric. Rubric: **Accuracy (0-2)**, **Completeness of required fields (0-2)**, **Tone/clarity (0-1)** — max 5 per output.

| Ticket | Model output | Accuracy | Completeness | Tone/Clarity | Total | One-line note |
|--------|--------------|----------|--------------|--------------|-------|---------------|
| Ticket 1: "my invoice shows a double charge and support never replied" | `{"category":"billing","summary":"Customer reports a double charge with no response.","sentiment":"NEGATIVE"}` | | | | | |
| Ticket 2: "is the mobile app down right now?" | `{"category":"technical","summary":"The app is definitely down company-wide.","sentiment":"NEUTRAL"}` | | | | | |
| Ticket 3: "thanks for fixing my account!" | `{"category":"general","summary":"This is a thank-you message.","sentiment":"POSITIVE"}` | | | | | |

**Where would human reviewers disagree with each other, and why?**
```
[Your answer - the point being: rubric scoring needs calibration too]
```

**Check your work:**
- [ ] All three tickets have numeric scores in every dimension
- [ ] Totals are correct sums, and scores differ across the tickets
- [ ] The disagreement note names where reviewers would legitimately differ (e.g., summary quality, not field presence)

---

## Exercise 3: Spot the Judge Bias

For each pair, decide which response an *unvalidated* LLM judge would likely prefer, and what bias explains it:

| Case | Response A | Response B | Unvalidated judge likely prefers... | Bias |
|------|-----------|-----------|--------------------------------------|------|
| 1 | "Category: billing. Summary: double charge." | "Based on a thorough analysis of the ticket, the customer appears to express concern about what may be a duplicated billing line item, which warrants escalation." | | |
| 2 | "Not enough info to classify — this ticket is ambiguous." | "This is clearly a technical issue and should be routed immediately." | | |
| 3 | Correct but terse JSON | Long JSON with several extra explanatory fields | | |

**What single mitigation (from 9.3) protects against all three?**
```
[Your answer]
```

**Check your work:**
- [ ] A bias is named for all three cases (verbosity, assertiveness/detail, extra fields)
- [ ] The single mitigation names a real 9.3 control (calibrate the judge against human labels / rubric-anchored judging) and explains why it covers all three

---

## Exercise 4: Versioning Checklist

You just ran an evaluation and scored 92 on your gold set — great. Six weeks later the same suite scores 76. Without more information you cannot tell why. List the seven things you'd want versioned (from Lesson 9.6) and mark which could silently explain a 16-point drop:

| What to version (9.6) | Could silently shift the score? |
|-----------------------|---------------------------------|
| | |
| | |
| | |
| | |
| | |
| | |

**One sentence: why is a prompt-score without versioning near-useless?**
```
[Your answer]
```

**Check your work:**
- [ ] The 9.6 versioning list is represented (dataset, prompt, model and params, judge, rubric/instructions, code, retrieval index)
- [ ] Items that could silently shift a score are marked — that's the point of the 92→76 mystery
- [ ] The one-sentence answer ties versioning to reproducibility and trust

---

## Exercise 5: Match Evaluation Depth to Risk

For each change, pick the evaluation profile from 9.7 and name the one extra thing you'd add:

| Change | Evaluation profile | Extra you'd add |
|--------|--------------------|-----------------|
| Rewording 2 lines of a prompt | | |
| Migrating from model A to model B | | |
| Changing a medical-advice assistant's safety rules | | |
| Updating the retrieval corpus of a RAG system | | |

**Check your work:**
- [ ] Profiles follow 9.7 risk matching (small offline change, migration A/B+canary, safety → adversarial + human review, RAG → retrieval + generation scored separately)
- [ ] Each "extra you'd add" is specific to that change, not the same generic answer in every row

---

## Reflection

1. Which evaluation step most protects against *regressions nobody has hit yet*?

2. Where in the pipeline (9.4) would a golden dataset of only synthetic examples betray you?

3. What's the cheapest control in this module, and why is it skipped so often?

---

# Challenge: Design an Evaluation Suite

## The Scenario

Design a complete evaluation suite for **your capstone prompt system** (the project this course has been building toward). Assume it's a real production feature with live users and a release pipeline. You are not writing final prompts here — you are designing the measurement system around them.

## Your Deliverable

Write a short design document covering:

**1. Dataset**
- Source of examples (real failures vs. synthetic, and where each comes from)
- Target size and the categories you'd deliberately include (edge cases, adversarial, no-answer, multilingual if relevant)

**2. Rubric & judge**
- The scoring dimensions and a 1-line definition of each
- How you will calibrate the LLM judge against human labels, and your acceptance threshold

**3. Pipeline stages (9.4)** — what runs at local, CI, pre-release, and production, and the gate at each

**4. Live rollout (9.5)** — how A/B and canary would apply to your system

**5. Versioning (9.6)** — your reproducibility checklist

**6. Risk-matched depth (9.7)** — how effort changes for small, migration, safety, and RAG-type changes to *your* system

---

## Design Document

```
[Your evaluation suite design]
```

**Check your work:**
- [ ] Dataset: a real-failure source is named, plus deliberate edge-case / adversarial / no-answer coverage
- [ ] Rubric: every scoring dimension has a one-line definition
- [ ] Judge calibration has an explicit acceptance threshold (a number, not "good enough")
- [ ] Pipeline maps to all four 9.4 stages with a gate at each
- [ ] A/B and canary rollout is described for this system specifically
- [ ] Versioning checklist covers the 9.6 items

---

## Evaluation Criteria

| Criteria | Points |
|----------|--------|
| Dataset: real-failure source identified + deliberate category coverage | 20 |
| Rubric: concrete, unambiguous scoring dimensions | 20 |
| Judge calibration plan with explicit acceptance threshold | 15 |
| Pipeline maps to all four 9.4 stages with gates | 20 |
| A/B + canary described for this system specifically | 10 |
| Full versioning checklist included | 10 |
| Risk-matched depth for at least two change types | 5 |
| **Total** | **100** |

---

## Bonus Challenge

Describe one failure mode your evaluation suite would miss — and what you'd add to catch it. (Honest answer: every eval suite has blind spots; the prize is naming yours.)

```
[Your answer]
```

**Check your work:**
- [ ] The blind spot is a real gap in YOUR design, not a generic known failure
- [ ] The addition you propose would actually catch it, with a mechanism (not "more testing")