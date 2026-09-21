# Module 11: Capstone Project

**Submission Checklist & Grading Rubric | Complete the other files first**

The checklist below is what a grader (or a teammate taking over your system) reasonably needs from you. The rubric is how the four deliverables map to a total 100 points.

---

## Final Submission Checklist

### Before you submit — self-review against each deliverable

**Deliverable 1: Full prompt system**
- [ ] System/role prompt documented as versioned prompt files (Module 10 discipline), not pasted loose in chat
- [ ] Structured output schema defined (field names, types, allowed values — Module 6)
- [ ] Hyperparameter recommendations justified in a short config note (Module 7)
- [ ] At least 2 edge cases / failure modes handled and documented
- [ ] Prompts and config named so a stranger can tell which file is which (`system_prompt.md`, `config.md`, etc.)

**Deliverable 2: Eval report**
- [ ] Golden dataset: ≥15 cases with expected/rubric-judgeable outputs
- [ ] Includes typical, edge, and ≥2 adversarial/no-answer cases
- [ ] Rubric defined explicitly before scoring
- [ ] Scoring recorded (human and/or judge), with any judge-calibration note
- [ ] Failure pattern + proposed fix stated in the summary

**Deliverable 3: Red-team report**
- [ ] ≥3 distinct attack attempts across >1 Module 8 category
- [ ] Each attempt: what was tried, observed result, verdict (blocked / partial / succeeded)
- [ ] Every success/partial has a matching patch + re-test confirmation
- [ ] Reflection paragraph on what you'd re-check after a future change

**Deliverable 4: Presentation/review**
- [ ] Why you chose the track and scope
- [ ] At least one honest iteration story — including something that didn't work
- [ ] What eval + red-team findings changed in your final system
- [ ] A concrete next step for another week of work

**Overall**
- [ ] Every prompt version you discuss is traceable (Module 10: version ids, why, and what changed)
- [ ] No real secrets/credentials committed anywhere in the submission
- [ ] All attack testing done only against your own fictional/isolated system

---

## Grading Rubric

| Deliverable | Criteria | Points |
|-------------|----------|--------|
| **D1 — Full prompt system** | Specific, non-generic system/role prompt (Module 5) | 8 |
| | Structured output with defined schema (Module 6) | 8 |
| | Reasoning-technique choice documented, with why over alternatives (Module 2/4) | 8 |
| | Hyperparameters justified for the use case (Module 7) | 8 |
| | ≥2 edge cases / failure modes handled (Module 1/6) | 8 |
| | *Subtotal* | *40* |
| **D2 — Eval report** | Golden dataset ≥15 cases incl. typical + edge + ≥2 adversarial/no-answer (Module 9.2) | 8 |
| | Rubric defined before scoring | 5 |
| | Scoring run (human and/or judge) with calibration noted if judge used (Module 9.3) | 8 |
| | Summary: pass rate + specific failure pattern + proposed fix | 4 |
| | *Subtotal* | *25* |
| **D3 — Red-team report** | ≥3 attacks across >1 category, incl. indirect injection where relevant (Module 8) | 8 |
| | Result + verdict documented per attempt | 5 |
| | Every success/partial patched and re-tested | 8 |
| | Reflection on re-checking after future changes | 4 |
| | *Subtotal* | *25* |
| **D4 — Presentation/review** | Track + scope choice explained | 2 |
| | Honest iteration story incl. a failure (Module 10) | 3 |
| | Eval + red-team findings shown to change the final system | 3 |
| | Concrete next step for another week | 2 |
| | *Subtotal* | *10* |
| **Total** | | **100** |

### Grade bands

| Score | Band | Interpretation |
|-------|------|----------------|
| 90-100 | **Excellent** | Ship-ready system with a defensible, documented process |
| 75-89 | **Solid** | Complete system; some justifications or edge coverage thin |
| 60-74 | **Developing** | Deliverables present but a key checklist item is missing or shallow |
| < 60 | **Revise** | Rework the weak deliverables and resubmit |

---

## Suggested Submission Layout

```
capstone_submission/
├── 01_prompt_system/
│   ├── system_prompt.md        # role/context prompt (Module 5)
│   ├── few_shot_examples.md    # if applicable (Module 3)
│   ├── edge_case_handling.md   # ≥2 failure modes documented
│   └── config.md               # hyperparameters + justification (Module 7)
├── 02_eval_report.md           # golden dataset, rubric, scores, failure pattern
├── 03_red_team_report.md       # attacks, results, patches, re-tests, reflection
├── 04_presentation.md          # track choice, iteration story, findings, next step
└── README.md                   # one-paragraph summary + pointer to each file
```

Adjust the layout to whatever fits your cohort's tooling — the requirement is that each checklist item is findable, not that it lives in a specific path.