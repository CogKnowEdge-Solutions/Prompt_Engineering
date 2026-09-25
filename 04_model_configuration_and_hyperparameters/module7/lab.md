# Lab: Temperature & Sampling Variance

## Objective

Run the same prompt at low, medium, and high temperature/top-p settings and compare output variance side by side.

---

## The Prompt

Use this same prompt for every run:

```
Write a one-sentence tagline for a sustainable coffee brand that donates
5% of profits to reforestation projects.
```

---

## Part 1: Low Temperature (≈0.1)

**Settings:**
```
temperature: 0.1
```

| Run | Output |
|-----|--------|
| 1 | |
| 2 | |
| 3 | |

**Observations:**
- How similar were the 3 outputs? _______________
- Did they differ at all? _______________
- Quality of first run (1-5)? _____

---

## Part 2: Medium Temperature (≈0.7)

**Settings:**
```
temperature: 0.7
```

| Run | Output |
|-----|--------|
| 1 | |
| 2 | |
| 3 | |

**Observations:**
- How similar were the 3 outputs? _______________
- Any standouts? _______________
- Quality of first run (1-5)? _____

---

## Part 3: High Temperature (≈1.2 or max supported)

**Settings:**
```
temperature: 1.2  (or your provider's max)
```

| Run | Output |
|-----|--------|
| 1 | |
| 2 | |
| 3 | |

**Observations:**
- How similar were the 3 outputs? _______________
- Any incoherent or off-topic results? _______________
- Quality of first run (1-5)? _____

---

## Part 4: Top-P Control

Now hold temperature at a medium 0.7 and vary top-p only:

| Setting | Run 1 | Run 2 | Run 3 | Variance (low/mid/high) |
|---------|-------|-------|-------|-------------------------|
| top_p = 0.3 | | | | |
| top_p = 0.7 | | | | |
| top_p = 0.95 | | | | |

---

## Part 5: Comparison Table

| Metric | Temp 0.1 | Temp 0.7 | Temp 1.2 | top-p 0.95 |
|--------|----------|----------|----------|------------|
| Similarity across runs (1-5) | | | | |
| Best single output (1-5) | | | | |
| Worst single output (1-5) | | | | |
| Would you run this task at this setting? | | | | |

---

## Part 6: Temperature vs. Seed

Pick the temperature and prompt from above, then run with a fixed seed 3 times:

| Setting | Run 1 | Run 2 | Run 3 |
|---------|-------|-------|-------|
| temp 0.7, seed=42 | | | |
| temp 0.7, seed=42 | | | |
| temp 0.7, seed=42 | | | |

**How reproducible was seeded output?** _______________

---

## Analysis Questions

1. **At which temperature did output become "too random" for this creative-but-controlled task?**

2. **Which matters more for this task — temperature or top-p?**

3. **What temperature would you pick for this tagline task, and why?**

4. **At what point does variance become a liability vs. a feature?**

---

## Key Takeaways

Fill in your observations:

- Best temperature for creativity: _______________
- Best temperature for consistency: _______________
- Did seed deliver determinism? _______________
- My recommended config for taglines: _______________