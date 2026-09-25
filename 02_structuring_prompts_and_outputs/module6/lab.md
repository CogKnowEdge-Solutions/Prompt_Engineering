# Lab: Extract Structured Data From Unstructured Text

## Objective

Turn messy, real-world text into clean, machine-readable JSON. You'll practice schema-first prompting, add few-shot examples, handle missing data, and verify your output with semantic checks.

---

## Part 1: The Input Data

Here are 5 real-world support emails (slightly messy on purpose). Your job is to extract the same fields from each.

```
1. "hi there, my order 78451 hasn't shipped yet. can u check?
   - rashid"

2. "Regarding invoice number 2201 - the amount looks wrong. I was
   charged twice last month. Best, Janet F."

3. "ORDER #33312 — the headphones arrived broken. (refund please)
   from: Miguel Rojas"

4. "can you help me set up my account?"

5. "Excellent service!!! Order 92013 arrived a day early, very happy.
   thanks again - Amanda"
```

---

## Part 2: Design Your Schema

Define the JSON schema you'll extract. Use these fields as a starting point:

- `customer_name` (string or null)
- `order_id` (integer or null)
- `issue_type` — one of: `REFUND`, `BILLING`, `SHIPPING`, `QUESTION`, `PRAISE`
- `urgency` — one of: `HIGH`, `MEDIUM`, `LOW`
- `summary` (one sentence)

**Your Schema (write it out):**
```
[Write your schema definition here]
```

**Missing-field policy:** What happens when a field is absent?
```
[State your policy explicitly]
```

---

## Part 3: Build a Schema-First Prompt

**Your Prompt:**
```
[Write your schema-first extraction prompt here]
```

**Test it on all 5 emails. Record the raw output you get:**

```
Email 1 output:
Email 2 output:
Email 3 output:
Email 4 output:
Email 5 output:
```

---

## Part 4: Validation

Now check each output against three layers. For each email:

| Email | Parses as JSON? | Matches schema? | Values make sense? |
|-------|-----------------|------------------|---------------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

**How many passed all three layers? ___/5**

**Where did failures happen?**
```
[Note the specific failures — parsing, schema, or semantic]
```

---

## Part 5: Add Few-Shot Examples

Add 2-3 few-shot examples that demonstrate:
- A typical extraction (contains all fields)
- A missing field case (use your null/sentinel policy)
- An ambiguous case (e.g., mixed sentiment)

**Your Improved Prompt With Examples:**
```
[Write your improved prompt here]
```

**Re-test all 5 emails:**

| Email | Parses? | Schema? | Semantics? |
|-------|---------|---------|------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |

**New score: ___/5**

---

## Part 6: Semantic Validation Check

The format check passes when the JSON is valid — but is the *content* right?

For each email, verify these specific claims from your extraction:

| Email | Expected | Your output | Correct? |
|-------|----------|-------------|----------|
| 1 | rashid, order 78451, SHIPPING, HIGH, no summary invention | | |
| 2 | Janet F., 2201, BILLING, HIGH | | |
| 3 | Miguel Rojas, 33312, REFUND, HIGH | | |
| 4 | null name, null order, QUESTION, LOW | | |
| 5 | Amanda, 92013, PRAISE, LOW | | |

**Semantic accuracy: ___/5**

---

## Analysis Questions

1. **Did the model ever invent a value that wasn't in the email? Where?**

2. **Which failure was more common: format errors or semantic errors?**

3. **How did few-shot examples change the results?**

4. **Would JSON mode have fixed your remaining problems? Why or why not?**

5. **Where would you add semantic validation in a real pipeline?**

---

## Key Takeaways

Fill in your observations:

- Biggest format problem: _______________
- Biggest semantic problem: _______________
- Did examples fix the format? _______________
- Did examples fix semantics? _______________
- What only a human check can catch: _______________