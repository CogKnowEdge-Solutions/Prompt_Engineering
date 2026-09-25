# Exercises: Constraint Challenge

## Instructions

For each exercise, you must satisfy **format + length + content** constraints in a single prompt. Design the prompt, then note any constraint that proved hard to satisfy.

---

## Exercise 1: Product Catalog Entry

**Input:**
```
SunnySound Wireless Earbuds - 24 hour battery life - waterproof - $89.99
- available now - 4.7 stars (1200 reviews) - free returns
```

**Required output:**
- **Format:** JSON with `name`, `price`, `features`, `rating`, `review_count`
- **Length:** `features` array max 3 items
- **Content:** only include facts present in the input

**Your Prompt:**
```
[Write your prompt here]
```

**Result:**
```
[Paste model output here]
```

**Constraints satisfied?** ☐ Format ☐ Length ☐ Content

**Check your work:**
- [ ] The prompt states the exact JSON structure (`name`, `price`, `features`, `rating`, `review_count`)
- [ ] The length rule (max 3 features) is stated in the prompt
- [ ] The content rule (only facts present in the input) is stated
- [ ] You pasted a real model output and verified each constraint against it
- [ ] The ☐ boxes match what the output actually did

---

## Exercise 2: Meeting Notes Extractor

**Input:**
```
Tuesday 10am — Q3 planning (Action items: Sarah sends deck EOD, Dev finishes
prototype by Friday, design review moved to Thursday 2pm. Budget discussion
deferred. Next meeting in 2 weeks.)
```

**Required output:**
- **Format:** Markdown table with columns `Item | Assignee | Deadline`
- **Length:** exactly the rows present (don't add rows)
- **Content:** copy names and deadlines exactly, no invented items

**Your Prompt:**
```
[Write your prompt here]
```

**Result:**
```
[Paste model output here]
```

**Constraints satisfied?** ☐ Format ☐ Length ☐ Content

**Check your work:**
- [ ] The prompt specifies the Markdown table and the three columns exactly (Item, Assignee, Deadline)
- [ ] The "exactly the rows present, no added rows" rule is stated
- [ ] The content rule (copy names and deadlines exactly) is stated
- [ ] The output has the correct row count and no invented entries

---

## Exercise 3: Document Classifier

**Input:**
```
RECEIPT-4471 | Paid: $124.50 | VISA x4444 | Date: 03/11 | Refund eligible: NO
```

**Required output:**
- **Format:** exactly one line: `TYPE|AMOUNT|PAYMENT_METHOD|DATE|REFUNDABLE`
- **Length:** one line, no explanation
- **Content:** values must match input exactly

**Your Prompt:**
```
[Write your prompt here]
```

**Result:**
```
[Paste model output here]
```

**Constraints satisfied?** ☐ Format ☐ Length ☐ Content

**Check your work:**
- [ ] The prompt specifies exactly one line with the 5 fields in order (TYPE|AMOUNT|PAYMENT_METHOD|DATE|REFUNDABLE)
- [ ] The "no explanation" rule is stated
- [ ] Every value in the output matches the input exactly
- [ ] The constraint boxes reflect the actual output, not your intent

---

## Exercise 4: JSON With Length Limit

**Input:**
```
The new Titan video card is a beast. It runs the latest games at 4K/120fps,
sips power, and stays quiet under load. But it costs $1,299 and some users
complain the software is buggy. Early buyers report card failures when
overclocking aggressively.
```

**Required output:**
- **Format:** JSON with `name`, `pros`, `cons`, `verdict`
- **Length:** pros/cons max 2 items each; `verdict` max 15 words
- **Content:** each item must trace to a specific sentence in the input

**Your Prompt:**
```
[Write your prompt here]
```

**Result:**
```
[Paste model output here]
```

**Constraints satisfied?** ☐ Format ☐ Length ☐ Content

**Check your work:**
- [ ] The prompt states the JSON structure and the length caps (pros/cons ≤2 items, verdict ≤15 words)
- [ ] The traceability rule (each item must trace to a specific sentence) is stated
- [ ] You can point to the input sentence behind each extracted item
- [ ] The verdict is actually ≤15 words and pros/cons are within 2 items

---

## Exercise 5: Strict CSV

**Input:**
```
Invoice #8890, due 12/15, items: "Web design $800", "Hosting $40/mo",
"Logo retainer $250". Client: Acme Co. Status: Past due.
```

**Required output:**
- **Format:** single CSV line with header `invoice,due_date,total,client,status`
- **Length:** exactly one data row
- **Content:** compute `total` from the listed amounts; no other values invented

**Your Prompt:**
```
[Write your prompt here]
```

**Result:**
```
[Paste model output here]
```

**Constraints satisfied?** ☐ Format ☐ Length ☐ Content

**Check your work:**
- [ ] The prompt specifies the single CSV line and the header column order
- [ ] The content rule (compute `total` from the listed amounts; nothing invented) is stated
- [ ] Your computed `total` is actually the sum — and you handled the monthly ($40/mo) item deliberately
- [ ] The output has exactly one data row

---

## Reflection Questions

1. Which constraint type was hardest to satisfy consistently — format, length, or content?

2. What prompt patterns best enforce each constraint type?

3. When you ran the same prompt twice, was the output stable? What would make it more stable?

---

# Challenge: Reliable JSON Every Time

## The Task

Build a prompt that extracts structured data reliably — **valid JSON on 5 out of 5 test runs**.

## The Extraction Task

Extract from a restaurant reservation email:

```
Fields:
- guest_name (string, or null if missing)
- party_size (integer)
- date (YYYY-MM-DD)
- time (HH:MM, 24h)
- special_requests (string array, empty if none)
- confidence ("HIGH" | "MEDIUM" | "LOW")
```

## The Test Input

```
email: "Hi! Table for 4 please this Saturday at 7:30 sharp. Birthday dinner
for my daughter — gluten-free cake if possible. — Linda"
```

## Your Build Steps

1. **Version 1 — no special handling.** Just your schema in the prompt. Run it 5 times. Record pass/fail (parses + matches schema).

2. **Version 2 — add "ONLY valid JSON" + explicit allowed values.** Re-run 5 times.

3. **Version 3 — add few-shot examples, including one that demonstrates output wrapped in code fences or JSON markers.** Re-run 5 times.

4. **Version 4 — add a `return JSON only, no commentary` instruction at the END of the prompt as well as the start, if it's still failing.**

## Results Table

| Version | Run 1 | Run 2 | Run 3 | Run 4 | Run 5 | Pass rate |
|---------|-------|-------|-------|-------|-------|-----------|
| V1 | | | | | | |
| V2 | | | | | | |
| V3 | | | | | | |
| V4 | | | | | | |

## Semantic Spot-Check

Even when JSON passes the format check, verify the *values* are right:

| Field | Expected | Extracted | Correct? |
|-------|----------|-----------|----------|
| guest_name | "Linda" | | |
| party_size | 4 | | |
| date | (the upcoming Saturday) | | |
| time | "19:30" | | |
| special_requests | ["gluten-free cake"] | | |
| confidence | HIGH (all info present) | | |

**Semantic accuracy: ___/6**

**Check your work:**
- [ ] All 4 versions were run 5 times each and the results table is fully filled
- [ ] The final version produced valid, schema-matching JSON on 5/5 runs
- [ ] The semantic spot-check is filled in and every wrong value is explained
- [ ] You can say which change (V2, V3, or V4) fixed the failures — that's the point of the exercise

---

## Evaluation Criteria

| Criteria | Points |
|----------|--------|
| 5/5 runs produce valid JSON (format) | 15 |
| Output matches schema (field names/types) | 10 |
| Semantic values correct | 10 |
| Few-shot examples used effectively | 5 |
| Missing-data policy demonstrated | 5 |
| Documentation of which change fixed the failures | 5 |
| **Total** | **50** |

---

## Bonus Challenge

Extend your prompt to also extract a phone number and handle the case where only a partial name is given ("just Linda").

**Check your work:**
- [ ] Phone-number extraction is tested both with and without a "+" prefix
- [ ] The partial-name case ("just Linda") is tested and your handling policy is documented (e.g., keep as given)
- [ ] The extended output still parses as valid JSON