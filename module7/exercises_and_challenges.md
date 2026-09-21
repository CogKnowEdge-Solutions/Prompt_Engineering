# Exercises: Constraint Challenge

## Instructions

For each exercise, hit a target length/format constraint using **parameters** (max_tokens, stop sequences, temperature, JSON mode, etc.) rather than prompt wording alone. Note where parameters can't do the job and wording still must.

---

## Exercise 1: Hard Length Cap

**Goal:** A 3-sentence product description — no more than ~40 words. Must never run long.

**Approach:**
```
Design parameter settings (max_tokens, stop sequences) that enforce this.
Settings:
max_tokens: ______
stop: ______
```

**Test:** Run 3 times, note actual word counts.

| Run | Word count | Within limit? |
|-----|------------|---------------|
| 1 | | |
| 2 | | |
| 3 | | |

**Which constraint needed parameters vs. prompt wording?**
```
[Your answer]
```

---

## Exercise 2: Cut Off at a Delimiter

**Goal:** A response that ends cleanly right after the second section, never running into a third unrequested section.

**Approach:**
```
Use stop sequences to cut generation at a natural boundary.
stop: ["______"]
```

**Test:** Show a truncated output that stops exactly where intended.

**Output:**
```
[Paste the cut-off output]
```

**Did the stop sequence work as a hard boundary?** _______________

---

## Exercise 3: JSON Only, No Commentary

**Goal:** Valid JSON output with zero surrounding text — no "Okay, here's:" preamble, no trailing notes.

**Approach:**
```
Use JSON mode / structured outputs (not just prompt wording).
response_format: ______
```

**Test:** Run 5 times, mark parsable.

| Run | Parses directly? |
|-----|------------------|
| 1 | |
| 2 | |
| 3 | |
| 4 | |
| 5 | |

**Did API-level format enforcement do what prompting couldn't? Why did it win?**
```
[Your answer]
```

---

## Exercise 4: Repetition Control

**Goal:** A 100-word explanation of a concept that does NOT repeat the same phrase more than twice.

**Approach:**
```
Use frequency/presence penalties (if your provider exposes them).
frequency_penalty: ______
presence_penalty: ______
```

**Test:** Count repeated phrases in the output.

| Run | Repeated phrases | Count |
|-----|------------------|-------|
| 1 | | |
| 2 | | |

**Did penalties work, or was your provider's support questionable here?**
```
[Your answer]
```

---

## Exercise 5: Reproducibility

**Goal:** Two calls that produce near-identical output.

**Approach:**
```
Use seed + low temperature.
seed: ______
temperature: ______
```

**Test:**

| Run | Output hash first 10 chars | Identical-ish? |
|-----|---------------------------|----------------|
| 1 | | |
| 2 | | |

**Was reproducibility perfect or best-effort? What drifted?**
```
[Your answer]
```

---

## Reflection

1. Which constraints are better handled by **parameters** than wording? Why?

2. Which constraints **only** wording can handle?

3. What did you learn about the limits of API-level enforcement?

---

# Challenge: Tune a Support Bot

## The Task

Balance **consistency against creativity** for a customer support bot that answers common billing questions. You must:
1. Pick a final configuration
2. Justify every single setting
3. Test that your config behaves as intended

## The Bot's Requirements

- Answers frequent questions consistently (repeated queries should read the same way)
- Occasionally offers a *slightly* varied phrasing so it doesn't feel robotic
- Always outputs valid JSON for structured field extraction
- Never burns tokens rambling — the billing answers should be tight
- Cost matters — the system prompt is reused across thousands of calls

## Your Configuration

```
temperature:          ______    justification: ______
top_p:                ______    justification: ______
max_tokens:           ______    justification: ______
stop:                 ______    justification: ______
frequency_penalty:    ______    justification: ______
presence_penalty:     ______    justification: ______
response_format:      ______    justification: ______
seed:                 ______    justification: ______
prompt_caching:       ______    justification: ______
reasoning_effort:     ______    justification: ______
```

## Test Plan

**Test 1 — Consistency:** Ask the same billing question 5 times. Rate how similar the answers are (1-5).

| Run | Answer similarity (1-5) |
|-----|-------------------------|
| 1-2 | |
| 2-3 | |
| 3-4 | |
| 4-5 | |

**Test 2 — Not robotic:** Ask 3 *different* variations of the same question. Does the bot vary phrasing appropriately without losing meaning?

```
[Your observations]
```

**Test 3 — Structured output:** Run the JSON extraction task. Does it parse 5/5?

```
[Results]
```

**Test 4 — Tight answers:** Measure average answer length. Is it near your target?

```
[Average length: ______ tokens]
```

## Justification Summary

Write one short paragraph defending the overall balance you chose — why this combination of consistency and creativity for a support bot, and where the edges of safety are.

```
[Your justification]
```

---

## Evaluation Criteria

| Criteria | Points |
|----------|--------|
| Each setting justified with reasoning | 15 |
| Tests show consistency target met | 10 |
| Tests show not-robotic variance | 10 |
| Structured output reliable | 5 |
| Token budget respected | 5 |
| Clear tradeoff thinking in final justification | 5 |
| **Total** | **50** |

---

## Bonus Challenge

Swap one configuration for the opposite extreme (e.g., temperature 1.5) and describe precisely what breaks.