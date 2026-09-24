# Prompt-Writing Cheat Sheet

*A one-page reference condensing Modules 1-10 for day-to-day use.*

---

## 1. Anatomy of a Prompt (Module 1)

```
TASK:        what you want, stated clearly, up front
CONTEXT:     background the model can't infer
AUDIENCE:    who this is for, and what they already know
FORMAT:      output shape (paragraph, list, table, JSON, ...)
CONSTRAINTS: length, tone, scope, restrictions (max 3-5)
EXAMPLES:    1-3 demonstrations of desired output (when needed)
```

**Ordering for long prompts (Module 3):** role/behavior first → context → instructions → examples → the specific input last.

---

## 2. Which Technique? (Modules 2, 4)

| Situation | Reach for |
|---|---|
| Simple, common task | Zero-shot |
| Specific format or style needed | Few-shot |
| Multi-step, fairly linear | Chain-of-Thought |
| Complex multi-step, isolated sub-problems | Least-to-most |
| High-stakes, want confidence in an answer | Self-consistency (+ verification) |
| Multiple valid approaches worth comparing | Tree-of-Thought (expensive — use sparingly) |
| Want tone/perspective | Role/persona (tone only — not accuracy) |
| Not sure where to start | A framework template (APE, RACE, CO-STAR, TAG) |

---

## 3. Structure (Module 3)

- **One instruction + one block of text** → plain delimiters (`"""text"""`, `---text---`)
- **Multiple distinct parts** → XML-style named tags (`<instructions>`, `<examples>`, `<ticket>` ...)
- **Markdown** → headings/bold labels work for short prompts; don't blend styles
- **Few-shot quality** → 3-5 diverse examples, each wrapped clearly, matching the exact output format you want back

---

## 4. Roles (Module 5)

- Be specific: *"senior tax accountant focused on small-business deductions"*, not *"helpful assistant"*
- Roles steer tone and emphasis, **not** correctness — test before assuming
- High-stakes domains (finance/health/legal): add over-trust protection ("AI, not licensed", "confirm with a professional")
- Skip the persona for simple lookups and pure accuracy tasks

---

## 5. Structured Output (Module 6)

1. Show the exact shape (schema-first)
2. Spell out allowed values for enum fields
3. Say "ONLY valid JSON" explicitly
4. Use a type notation (`"order_id": integer`)
5. **Decide missing-data policy up front**: `null` vs `"unknown"` — never invent
6. Keep field names stable (they're a contract)
7. Prefer API-level **schema enforcement** > **JSON mode** > prompting alone
8. **Schema conformance ≠ correctness** — keep semantic validation separate:

```
1. Format check:   does it parse?
2. Schema check:   are keys/types right?
3. Semantic check: are the VALUES right?
```

---

## 6. Hyperparameters (Module 7)

| Dial | Low | High | Notes |
|---|---|---|---|
| temperature | predictable | varied | tune temp *or* top-p, not both |
| max_tokens | cheap, can truncate | costs more | watch thinking tokens on reasoning models |
| stop sequence | cut at boundary | — | not supported on some reasoning models |
| frequency/presence penalty | less repetition | — | not available everywhere; test |
| seed | more reproducible | — | best-effort, never byte-guaranteed |
| reasoning_effort | cheaper/faster | deeper | not automatically better |
| prompt_caching | big cost lever | — | fragile to config changes |

Config rule: extraction = cold (temp ~0.1, strict format, caching on); brainstorming = hot (temp ~0.8+, no format constraint).

---

## 7. Security Quick Checks (Module 8)

- [ ] Untrusted content (documents, webpages, emails, tool outputs) segregated from instructions
- [ ] System instructions structurally distinct (instruction hierarchy)
- [ ] Agent/tool access is least-privilege and scoped
- [ ] Output validated before any consequential action
- [ ] Human confirmation for sensitive actions
- [ ] Critical controls enforced in code, not just prompt wording
- [ ] Red-team set re-run on every prompt version change

---

## 8. Evaluation (Module 9)

1. Golden dataset **from real failures** (+ edge, adversarial, no-answer cases)
2. Sanity checks first, judged scoring only on what passes
3. Calibrate your LLM judge against human labels (target ~85-90% agreement)
4. Gate at each stage: local → CI → pre-release adversarial → production monitoring
5. Version: dataset, prompt, model, parameters, judge, retrieval corpus
6. A/B test + canary-roll anything that looks good offline

---

## 9. Iteration Loop (Module 10)

1. Form a specific, falsifiable hypothesis
2. Make **one** isolated change
3. Run the evaluation suite + adversarial set
4. Compare against the previous version's scores
5. Promote / reject / iterate — from the comparison, not intuition
6. Record what changed and why (including rejected attempts)
7. Rollback = return to last known-good version

---