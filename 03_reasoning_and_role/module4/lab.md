# Lab: Solve a Multi-Step Problem With and Without CoT

## Objective

Solve the same multi-step math/logic problem with and without Chain-of-Thought prompting, then compare accuracy, token cost, and reliability.

---

## Part 1: The Problem

Use this problem for all parts of the lab:

```
A bakery sold 240 cupcakes on Monday. On Tuesday it sold 25% fewer
cupcakes than Monday. On Wednesday it sold 15 more cupcakes than
Tuesday. Each cupcake costs $3.50. How much money did the bakery
make over the three days?
```

**Correct answer:** Compute it yourself first before testing the model.

Your answer: _______________

---

## Part 2: Direct Answer (No CoT)

**Prompt:**
```
A bakery sold 240 cupcakes on Monday. On Tuesday it sold 25% fewer
cupcakes than Monday. On Wednesday it sold 15 more cupcakes than
Tuesday. Each cupcake costs $3.50. How much money did the bakery
make over the three days?
```

**Model's Answer:**
[Paste the model's response here]

**Was it correct?** ☐ Yes ☐ No

**Token count:** _____ tokens

---

## Part 3: Chain-of-Thought Prompting

**Prompt:**
```
A bakery sold 240 cupcakes on Monday. On Tuesday it sold 25% fewer
cupcakes than Monday. On Wednesday it sold 15 more cupcakes than
Tuesday. Each cupcake costs $3.50. How much money did the bakery
make over the three days?

Let's think step by step.
```

**Model's Answer:**
[Paste the model's response here]

**Was it correct?** ☐ Yes ☐ No

**Token count:** _____ tokens

---

## Part 4: Run It Multiple Times (Self-Consistency)

Run the CoT prompt 5 times and record each answer:

| Run | Final Answer | Correct? |
|-----|--------------|----------|
| 1 | | |
| 2 | | |
| 3 | | |
| 4 | | |
| 5 | | |

**Most common answer:** _______________

**Agreement:** ___/5

---

## Part 5: Comparison

| Metric | Direct | CoT | Self-Consistency (5x) |
|--------|--------|-----|------------------------|
| Correct? | | | |
| Tokens used | | | |
| Time to answer | | | |
| Confidence in answer | | | |
| Cost (relative) | $ | $$ | $$$ |

---

## Part 6: Test On Simpler Problems

Try these on both the direct and CoT prompts:

**Problem A:** What is 15% of 200?

| Version | Answer | Correct? |
|---------|--------|----------|
| Direct | | |
| CoT | | |

**Problem B:** If a train travels 60 mph for 2.5 hours, how far does it go?

| Version | Answer | Correct? |
|---------|--------|----------|
| Direct | | |
| CoT | | |

---

## Analysis Questions

1. **Did CoT improve accuracy on the complex problem? On the simple ones?**

2. **How much more did CoT cost in tokens?**

3. **At what point is CoT "not worth it"?**

4. **Did self-consistency catch any errors that a single CoT run missed?**

5. **What kind of problem genuinely needs CoT, versus one where it's overkill?**

---

## Key Takeaways

Fill in your observations:

- CoT helped most on: _______________
- CoT was overkill on: _______________
- Self-consistency value: _______________
- Surprising result: _______________
