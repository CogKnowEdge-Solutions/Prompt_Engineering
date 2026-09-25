# Lab: Build a Classifier Prompt Using Few-Shot Examples

## Objective

Build a sentiment classifier using few-shot examples. You'll start with a basic version and improve it by adjusting example diversity.

---

## Part 1: Build a Basic Classifier

### Task
Create a few-shot prompt that classifies customer reviews as Positive, Negative, or Neutral.

### Step 1: Write Your First Classifier

**Your Prompt:**
```
[Write your few-shot classifier prompt here with 3-5 examples]
```

### Step 2: Test With These Reviews

| Review | Your Classification | Correct? |
|--------|---------------------|----------|
| "Best purchase ever!" | | |
| "Completely useless product" | | |
| "It works fine I guess" | | |
| "Great quality but too expensive" | | |
| "Arrived on time, as described" | | |

**Accuracy: ___/5**

---

## Part 2: Analyze Your Examples

### Questions About Your Examples

1. What types of reviews did you include as examples?
   - All positive? All negative? Mix?

2. Did any test review confuse your classifier? Which one?

3. Why do you think it failed on that review?

---

## Part 3: Improve by Adding Diversity

### Step 1: Add Edge Cases

Rewrite your prompt with more diverse examples that cover:
- Mixed sentiments (good AND bad in same review)
- Sarcasm or irony
- Neutral with slight positive/negative lean
- Very short reviews
- Very long reviews

**Your Improved Prompt:**
```
[Write your improved prompt with diverse examples]
```

### Step 2: Test Again

| Review | Your Classification | Correct? |
|--------|---------------------|----------|
| "Best purchase ever!" | | |
| "Completely useless product" | | |
| "It works fine I guess" | | |
| "Great quality but too expensive" | | |
| "Arrived on time, as described" | | |
| "Not bad, not great" | | |
| "Sure, if you like wasting money" | | |
| "AMAZING!!!!!" | | |
| "The product is okay but customer service was rude" | | |

**Accuracy: ___/9**

---

## Part 4: Compare Results

### Before vs. After

| Metric | Basic (Part 1) | Improved (Part 3) |
|--------|----------------|-------------------|
| Number of examples | | |
| Types of examples | | |
| Accuracy on test set | | |
| Confusing reviews | | |

### Analysis Questions

1. **How much did accuracy improve?**

2. **Which specific examples helped the most?**

3. **What pattern do you notice about good examples vs bad examples?**

4. **Is there a tradeoff between number of examples and accuracy?**

---

## Part 5: Test Edge Cases

Try these tricky reviews on both versions:

| Review | Basic Classifier | Improved Classifier |
|--------|------------------|---------------------|
| "I've seen better at a dollar store" | | |
| "Five stars!" | | |
| "It's not the worst" | | |
| "Would buy again but it broke" | | |

**Which version handled these better? Why?**

---

## Key Takeaways

Fill in your observations:

- Minimum examples needed for good accuracy: ___
- Most important type of example to include: ___
- Biggest improvement from: ___
- Surprising edge case: ___
