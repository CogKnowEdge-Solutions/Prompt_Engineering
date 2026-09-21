# Lab: Same Task, 3 Different Personas

## Objective

Run the same task with three different personas — expert, teacher, and critic — and compare how tone, emphasis, and usefulness change while the underlying task stays identical.

---

## The Task

Use this task for all three personas:

```
Explain how compound interest works.
```

---

## Part 1: Expert Persona

**Your Prompt:**
```
You are a senior financial analyst with 20 years of experience managing
investment portfolios. Explain how compound interest works.
```

**Output:**
[Paste the model's response here]

**Observations:**
- Primary tone: _______________________
- Vocabulary level: _______________________
- What it emphasized: _______________________
- What it left out: _______________________
- How useful was it for a beginner (1-5)? _____

---

## Part 2: Teacher Persona

**Your Prompt:**
```
You are a patient, encouraging high school math teacher who loves explaining
concepts with relatable everyday examples. Explain how compound interest works.
```

**Output:**
[Paste the model's response here]

**Observations:**
- Primary tone: _______________________
- Vocabulary level: _______________________
- What it emphasized: _______________________
- What it left out: _______________________
- How useful was it for a beginner (1-5)? _____

---

## Part 3: Critic Persona

**Your Prompt:**
```
You are a skeptical financial journalist who questions common assumptions
and points out where popular advice falls short. Explain how compound
interest works.
```

**Output:**
[Paste the model's response here]

**Observations:**
- Primary tone: _______________________
- Vocabulary level: _______________________
- What it emphasized: _______________________
- What it left out: _______________________
- How useful was it for a beginner (1-5)? _____

---

## Part 4: Control (No Persona)

**Your Prompt:**
```
Explain how compound interest works.
```

**Output:**
[Paste the model's response here]

---

## Part 5: Comparison

| Aspect | Expert | Teacher | Critic | Control (none) |
|--------|--------|---------|--------|----------------|
| Tone | | | | |
| Accuracy (1-5) | | | | |
| Clarity (1-5) | | | | |
| Engagement (1-5) | | | | |
| Relevance for a beginner (1-5) | | | | |

---

## Part 6: Test for Accuracy Difference

The research says personas mostly change tone, not accuracy. Run this factual check with each persona:

```
What is 27% of 340?
```

| Persona | Answer | Correct? |
|---------|--------|----------|
| Expert | | |
| Teacher | | |
| Critic | | |
| Control | | |

---

## Analysis Questions

1. **Which persona produced the best explanation? For whom?**

2. **Did accuracy change across personas? What does that suggest?**

3. **Which persona, if any, added real value over the control? Which added token cost without value?**

4. **If you were building a finance app, which persona would you use and where would you add the over-trust disclaimer?**

---

## Key Takeaways

Fill in your observations:

- Role prompting changed ______ the most
- Role prompting barely affected ______
- Best use of a persona: _______________
- Where I'd skip the persona: _______________
- Surprising result: _______________