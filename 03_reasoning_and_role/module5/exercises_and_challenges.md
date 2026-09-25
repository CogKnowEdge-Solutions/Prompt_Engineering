# Exercises: From-Scratch Prompt Design

## Instructions

For each exercise, you're given only a goal. Design a complete prompt from scratch — including role (if useful), context, audience, and constraints. Justify your choices at the end.

---

## Exercise 1: Goal Only

**Goal:** Get a 5-paragraph essay on renewable energy for a 10th grade science class, formatted with headings.

**Your Complete Prompt:**
```
[Write your prompt here]
```

**Check your work:**
- [ ] The audience is explicit (10th grade science) and the reading level matches it
- [ ] Output shape is specified: 5 paragraphs, headings, renewable-energy topic
- [ ] Format and length constraints are concrete, not vague
- [ ] A role is used only where it adds value (or skipped deliberately)

---

## Exercise 2: Goal Only

**Goal:** Get a short email declining a job offer politely, with a reason that doesn't burn bridges.

**Your Complete Prompt:**
```
[Write your prompt here]
```

**Check your work:**
- [ ] The goal (declining politely) and the tension (a reason without burning bridges) are both addressed
- [ ] Tone guidance is explicit (polite, appreciative, short)
- [ ] Output shape is specified (a short email, not an essay)
- [ ] A role is used only where it adds value (or skipped deliberately)

---

## Exercise 3: Goal Only

**Goal:** Get a step-by-step guide to fix a slow Windows computer, suitable for someone non-technical.

**Your Complete Prompt:**
```
[Write your prompt here]
```

**Check your work:**
- [ ] Audience is explicit (non-technical person) and jargon is constrained
- [ ] Output shape is a step-by-step guide with ordered steps
- [ ] The prompt says what to include (causes and fixes) and what to avoid (registry/tool fear)
- [ ] A role is used only where it adds value (or skipped deliberately)

---

## Exercise 4: Goal Only

**Goal:** Get code review feedback on your Python script. You want security and performance issues prioritized.

**Your Complete Prompt:**
```
[Write your prompt here]
```

**Check your work:**
- [ ] The review has explicit priorities: security and performance first
- [ ] Output shape is specified (a prioritized comment list, not a prose essay)
- [ ] The prompt says what to ignore or downgrade (style nits)
- [ ] A role is used only where it adds value (or skipped deliberately)

---

## Exercise 5: Goal Only

**Goal:** Get three different marketing taglines for a sustainable clothing brand, one for each target segment (young adults, parents, corporate buyers).

**Your Complete Prompt:**
```
[Write your prompt here]
```

**Check your work:**
- [ ] All three target segments (young adults, parents, corporate) are named and differentiated
- [ ] Output shape is exactly three taglines, one per segment
- [ ] Brand constraints (sustainable) are present in the prompt
- [ ] A role is used only where it adds value (or skipped deliberately)

---

## Exercise 6: Goal Only

**Goal:** Get an explanation of how the blockchain works that's accurate but simple enough for your grandmother.

**Your Complete Prompt:**
```
[Write your prompt here]
```

**Check your work:**
- [ ] Audience is explicit (needs a simple explanation for a non-technical person)
- [ ] Accuracy and simplicity are both addressed — you traded jargon for analogy deliberately
- [ ] Output shape is an explanation, not a definition
- [ ] A role is used only where it adds value (or skipped deliberately)

---

## Justification

For each exercise, answer:

| Ex | Did you use a role? | Why or why not? | What context did you add? |
|----|--------------------|-----------------|---------------------------|
| 1 | | | |
| 2 | | | |
| 3 | | | |
| 4 | | | |
| 5 | | | |
| 6 | | | |

---

## Reflection Questions

1. For which goals did a role actually add value? Where was it unnecessary?

2. Which goals were mostly about accuracy vs. mostly about tone?

3. Did you ever combine role with broader context? How?

---

# Challenge: Design a System Prompt

## Task

Design a complete **system prompt** for a production assistant of your choice. Pick ONE:

- A customer support bot for an e-commerce store
- A math tutor for middle school students
- A code review assistant for a dev team
- A travel planning assistant
- A personal budgeting assistant
- Your own use case

## Requirements

Your system prompt must include:

1. **Role/persona** — with justification (and remember the research from 5.2)
2. **Audience** — who the assistant is serving
3. **Tone & style guidance**
4. **Behavioral rules** — what to do and what to avoid
5. **Constraints** — length, format, disclaimers
6. **Context handling** — what it should ask the user for vs. assume
7. **Over-trust protection** — a disclaimer or verification prompt, if the domain is high-stakes

## Your System Prompt

```
[Write your complete system prompt here]
```

---

## Self-Review Checklist

Before submitting, check each item:

- [ ] Role is specific, not generic ("helpful assistant")
- [ ] Role is appropriate for the domain (or skipped if not needed)
- [ ] Tone guidance is clear
- [ ] Behavioral rules cover what NOT to do
- [ ] Constraints are concrete (length, format)
- [ ] Over-trust risk addressed for high-stakes domains
- [ ] Context setting beyond just the role label

---

## Evaluation Criteria

| Criteria | Points |
|----------|--------|
| Specific, well-chosen role (or justified absence) | 10 |
| Clear audience and tone guidance | 10 |
| Concrete behavioral rules and constraints | 10 |
| Broader context setting beyond role | 10 |
| Over-trust protection for high-stakes domain | 5 |
| Applied Module 5 research findings (no blind trust in personas) | 5 |
| **Total** | **50** |

---

## Bonus Challenge

Using your system prompt, run the same user question with and without the persona line. Compare the outputs and note whether the persona changed tone, accuracy, or both.

**Check your work:**
- [ ] You ran the same question with and without the persona line (not just one version)
- [ ] Your comparison separates tone changes from accuracy changes
- [ ] Your conclusion reflects the 5.2 research: personas tend to shift tone more than accuracy
- [ ] You judged accuracy against a reference answer, not by how it "sounds" better