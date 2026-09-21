# Lab: Comparing Prompting Techniques

## Objective

Solve the same task using 3 different prompting techniques and compare the quality, cost, and speed of each approach.

---

## Task: Explain Quantum Computing

You will explain quantum computing to a beginner using three different techniques.

---

## Part 1: Zero-Shot Prompting

**Prompt:**
```
Explain quantum computing to a beginner.
```

**Your Output:**
[Paste the model's response here]

**Notes:**
- Number of tokens used: _____
- Time to generate: _____
- Quality (1-5): _____

---

## Part 2: Chain-of-Thought Prompting

**Prompt:**
```
Explain quantum computing to a beginner.

Think step by step:
1. Start with what regular computers do
2. Explain the problem quantum computers solve
3. Explain how qubits work differently
4. Give a real-world example of what it can do
5. Summarize in one sentence
```

**Your Output:**
[Paste the model's response here]

**Notes:**
- Number of tokens used: _____
- Time to generate: _____
- Quality (1-5): _____

---

## Part 3: Role-Based + Few-Shot Prompting

**Prompt:**
```
You are a science teacher explaining concepts to 10-year-olds.

Explain quantum computing using this style:

Example 1:
Topic: Electricity
Explanation: "Imagine tiny invisible messengers running through wires, 
carrying your messages and powering your lights. They're so fast they 
can travel around the world in one second!"

Example 2:
Topic: DNA
Explanation: "Think of DNA like a recipe book inside every cell of your 
body. It tells your body how to build you - your eye color, your hair, 
even how tall you'll grow!"

Now explain quantum computing in the same style:
```

**Your Output:**
[Paste the model's response here]

**Notes:**
- Number of tokens used: _____
- Time to generate: _____
- Quality (1-5): _____

---

## Part 4: Comparison Analysis

### Quality Comparison

| Criteria | Zero-Shot | Chain-of-Thought | Role + Few-Shot |
|----------|-----------|------------------|-----------------|
| Accuracy | | | |
| Clarity | | | |
| Engagement | | | |
| Appropriate for beginner? | | | |
| Overall Quality (1-5) | | | |

### Cost Comparison

| Metric | Zero-Shot | Chain-of-Thought | Role + Few-Shot |
|--------|-----------|------------------|-----------------|
| Input tokens | | | |
| Output tokens | | | |
| Total tokens | | | |
| Estimated cost (at $0.03/1K tokens) | | | |

### Speed Comparison

| Metric | Zero-Shot | Chain-of-Thought | Role + Few-Shot |
|--------|-----------|------------------|-----------------|
| Time to write prompt | | | |
| Time to generate | | | |
| Time to review/edit | | | |
| Total time | | | |

---

## Analysis Questions

1. **Which technique produced the best quality output? Why?**

2. **Which technique was most cost-effective? Why?**

3. **Which technique was fastest end-to-end? Why?**

4. **If you had to use this in production, which would you choose and why?**

5. **What are the tradeoffs you observed between quality and cost?**

---

## Key Takeaways

Fill in your observations:

- Best for quick tasks: _______________
- Best for accuracy: _______________
- Best for engagement: _______________
- Best for production: _______________
- Biggest surprise: _______________
