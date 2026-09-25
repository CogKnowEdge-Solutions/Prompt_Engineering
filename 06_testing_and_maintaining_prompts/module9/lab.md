# Lab: Build an Evaluation Suite

## Objective

Bootstrap the full evaluation workflow from Lesson 9.2-9.5 on a small, fictional scale: build a 10-example golden dataset (Lab A), calibrate an LLM-as-judge against your own human scores (Lab B), then run a mini A/B test between two prompt variants and pick a winner (Lab C).

## The Task Under Evaluation (fictional)

**TriageBot** reads a support ticket and returns JSON: `category` (one of `technical`, `billing`, `general`), `summary` (one sentence), `sentiment` (`POSITIVE`, `NEUTRAL`, `NEGATIVE`). Everything here is fictional — no real tickets, no real data.

**Prompt Variant A (to evaluate in Lab A):**
```
Classify the support ticket into technical/billing/general.
Write a one-sentence summary. Return JSON with
category, summary, and sentiment (POSITIVE/NEUTRAL/NEGATIVE).
Ticket: {{TICKET}}
```

---

## Lab A: Build a 10-Example Golden Dataset

Create 10 fictional tickets. Include at least one of each deliberately tricky category: an edge case, an adversarial/ambiguous input, a "no correct answer" case, a non-English ticket, and a praise note (no issue at all). For each, write the **expected output** (or enough detail to judge a new output against it).

| # | Your fictional ticket | Expected category | Expected sentiment | Notes a judge should check |
|---|-----------------------|-------------------|--------------------|----------------------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |
| 9 | | | | |
| 10 | | | | |

**Score your dataset design:** which of your 10 deliberately targets the "confident invention" failure mode?
```
[Your answer]
```

---

## Lab B: LLM-as-Judge vs. Human Scoring

**Step 1 — Human scores:** run Variant A on your 10 tickets, then score each output yourself with this rubric: **Accuracy (0-2), Field completeness (0-2), Clarity (0-1)**.

| # | Accuracy | Completeness | Clarity | Human total |
|---|----------|--------------|---------|-------------|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |
| 4 | | | | |
| 5 | | | | |
| 6 | | | | |
| 7 | | | | |
| 8 | | | | |
| 9 | | | | |
| 10 | | | | |

**Step 2 — Judge run:** write a judge prompt with an explicit rubric (specific criteria, so it doesn't just reward length). Run the judge on the same 10 outputs.

```
My judge prompt:
[Paste the judge prompt]
```

| # | Human total | Judge score | Agree? (within 1 point) |
|---|-------------|-------------|--------------------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |
| 7 | | | |
| 8 | | | |
| 9 | | | |
| 10 | | | |

**Step 3 — Agreement:** compute your agreement rate. Lesson 9.3's target is roughly 85-90%.

```
Agreement: ______ / 10 = ______%
```

**Step 4 — Calibrate (only if below target):** what would you change in the judge prompt (specific criteria? few-shot scoring examples?), then re-run.

```
[What you changed and the new agreement rate]
```

**Step 5 — Bias check:** did the judge favor long, confident answers on any item? Where?
```
[Your observations]
```

---

## Lab C: A/B Test Two Prompt Variants

**Variant B** (few-shot — pulls in Module 3 technique):
```
You classify support tickets. Examples:
Ticket: "wifi keeps dropping" -> technical
Ticket: "i was charged twice" -> billing
Ticket: "what are your hours?" -> general
Now classify this ticket and write a one-sentence summary + sentiment:
{{TICKET}}
```

Run **Variant A** and **Variant B** on 20 inputs (add 10 more fictional tickets). Score all 40 outputs with your calibrated judge.

**Results table:**

| Input # | Variant A score | Variant B score | Variant B JSON valid (sanity check)? |
|---------|-----------------|-----------------|--------------------------------------|
| 1 | | | |
| ... to 20 | | | |

**Cross-check:** on the 10 examples you graded by hand in Lab B, did the judge's A-vs-B preference match your human preference?
```
[Your comparison]
```

**Decision:** which variant wins, and on what basis (average score, consistency, sanity-check pass rate, cost)? Remember 9.5: an offline winner still needs a canary in real traffic.

```
[Your winner + reasoning]
```

---

## Analysis Questions

1. Where in these labs did **sanity checks** save you from wasting judge-level effort?

2. Was judge agreement harder to hit on some ticket categories than others? Which, and why?

3. If the judge and a human disagreed on a ticket, who was usually right — and how would you handle that permanently (9.3)?

4. Your A/B winner was chosen offline. What real-traffic metric would you watch before fully rolling it out (9.5)?

---

## Key Takeaways

Fill in your observations:

- My judge agreed with human scoring at ______%
- The bias I most often saw in the judge: _______________
- A/B winner: _______________, but I'd still canary on: _______________
- The next dataset additions I'd make (from real failures): _______________

---

**Note:** all tickets and data in this lab are fictional. Reuse this workflow on any real system's logs only with proper approval and anonymization.