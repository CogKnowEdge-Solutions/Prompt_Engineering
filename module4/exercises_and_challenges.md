# Exercises: Fix-the-Prompt & Before/After

## Exercise 1: Fix-the-Prompt (Force Step-by-Step Reasoning)

Rewrite each prompt so the model is forced to reason step by step before answering.

---

### 1.1: The Direct Math Prompt

**Original Prompt:**
```
What is 37 × 48?
```

**Your Improved Prompt:**
```
[Write your improved prompt here]
```

**Why this works:** _______________________

---

### 1.2: The Jumping-to-Conclusion Prompt

**Original Prompt:**
```
Should our company adopt a 4-day work week?
```

**Your Improved Prompt:**
```
[Write your improved prompt here]
```

**Why this works:** _______________________

---

### 1.3: The Logic Puzzle Prompt

**Original Prompt:**
```
Who owns the fish?
```

*(Context: There are 5 houses in a row, each a different color, inhabited by people of different nationalities who drink different beverages, smoke different brands, and keep different pets...)*

**Your Improved Prompt:**
```
[Write your improved prompt here]
```

**Why this works:** _______________________

---

### 1.4: The Multi-Part Word Problem

**Original Prompt:**
```
If I invest $5,000 at 7% annual interest compounded monthly for 3 years, how much will I have?
```

**Your Improved Prompt:**
```
[Write your improved prompt here]
```

**Why this works:** _______________________

---

### 1.5: The Diagnosis Prompt

**Original Prompt:**
```
Why is my website slow?
```

**Your Improved Prompt:**
```
[Write your improved prompt here]
```

**Why this works:** _______________________

---

## Exercise 2: Before/After Comparison

For each pair, note which prompting approach is best and why.

---

### 2.1: Simple Lookup vs. Multi-Step

**Scenario A:**
```
What's the capital of Australia?
```

**Scenario B:**
```
If I fly from Sydney to the capital of Australia, then to Perth,
how many time zones do I cross and in which direction?
```

**Which needs CoT?** _______________

**Why?** _______________________

---

### 2.2: One Correct Method vs. Multiple Approaches

**Scenario A:**
```
What is 144 ÷ 12?
```

**Scenario B:**
```
Design three different pricing strategies for a subscription app
and recommend the best one.
```

**Which needs ToT?** _______________

**Why?** _______________________

---

### 2.3: Low-Stakes vs. High-Stakes

**Scenario A:**
```
Suggest a name for my new coffee shop.
```

**Scenario B:**
```
Calculate the correct dosage for a prescription based on patient weight
and medical history.
```

**Which needs self-consistency?** _______________

**Why?** _______________________

---

### 2.4: Linear vs. Branching Problem

**Scenario A:**
```
Calculate the total cost of a shopping list with 12 items.
```

**Scenario B:**
```
Plan a route that visits 6 cities with the shortest total travel time.
```

**Which needs a more advanced technique?** _______________

**Why?** _______________________

---

## Reflection Questions

1. What trigger phrases reliably force step-by-step reasoning?

2. When is CoT overkill?

3. Why doesn't self-consistency fix systematic errors?

4. What kinds of problems have "multiple valid approaches"?

---

# Challenge: Debug a Reasoning Failure

## Scenario

A student wrote a Chain-of-Thought prompt to solve a word problem, but the model still got the wrong answer — and the reasoning looked confident the whole way.

## The Problem

```
A tank can be filled by Pipe A in 4 hours and by Pipe B in 6 hours.
If both pipes are opened together, how long will it take to fill the tank?
```

**Correct answer:** 2.4 hours (or 2 hours 24 minutes)

## The Failing Prompt

```
A tank can be filled by Pipe A in 4 hours and by Pipe B in 6 hours.
If both pipes are opened together, how long will it take to fill the tank?
Let's think step by step.
```

## The Model's (Wrong) Reasoning

```
Step 1: Pipe A fills the tank in 4 hours, so its rate is 1/4 tank per hour.
Step 2: Pipe B fills the tank in 6 hours, so its rate is 1/6 tank per hour.
Step 3: Together their combined rate is 1/4 + 1/6.
Step 4: 1/4 + 1/6 = 2/6 + 3/6 = 5/6 tank per hour.
Step 5: Time = 1 ÷ (5/6) = 6/5 = 1.2 hours.

Answer: 1.2 hours
```

*(Hint: Steps 1-3 and Step 5 are correct. Step 4 is wrong — check the arithmetic.)*

---

## Your Task

### Step 1: Find the Error

Where exactly is the reasoning mistake? Answer in one sentence.

```
[Your answer]
```

### Step 2: Diagnose Why It Happened

Was this a random error or a systematic one? How can you tell?

```
[Your answer]
```

### Step 3: Fix the Prompt

Rewrite the prompt so the model is more likely to catch this kind of arithmetic mistake. Consider:
- Asking the model to verify each step before proceeding
- Asking it to double-check fractions separately
- Using least-to-most to isolate the addition step
- Combining CoT with self-consistency

**Your Fixed Prompt:**
```
[Write your improved prompt here]
```

### Step 4: Test Your Fix

Run your fixed prompt. Did it get 2.4 hours? Record the result.

```
[Paste result here]
```

### Step 5: Would Self-Consistency Have Helped?

Run the *original* failing prompt 5 times. How many runs got it wrong?

| Run | Answer | Correct? |
|-----|--------|----------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |

**Verdict:** Would majority voting have saved it? _______________

### Step 6: Explain the Lesson

In 2-3 sentences, explain what this exercise teaches about the limits of Chain-of-Thought and self-consistency.

```
[Your answer]
```

---

## Evaluation Criteria

| Criteria | Points |
|----------|--------|
| Correctly identifies the arithmetic error | 10 |
| Distinguishes random vs. systematic error | 10 |
| Fixed prompt produces correct answer | 10 |
| Reasoning about self-consistency is accurate | 5 |
| Clear explanation of the lesson | 5 |
| **Total** | **40** |

---

## Bonus Challenge

Create your own "confidently wrong" reasoning example — a prompt where the model reaches a plausible but incorrect answer — and show how you'd fix it.
