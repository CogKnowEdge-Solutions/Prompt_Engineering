# LLM Tooling Index

*A short, course-wide index of practical tooling for red-teaming (Module 8) and evaluation (Module 9).*

**Read this first:** the LLM tooling landscape moves fast — names are frequently renamed, acquired, or deprecated. Every entry below is a *category* pointer; verify current documentation, licenses, and supported models before building on anything. Nothing here is an endorsement — pick tools that fit your stack, and always re-test them against your own system.

---

## 1. Red-Teaming & Security Testing (Module 8)

These run automated attack suites against your prompt system, useful for *breadth* and *regression coverage* — complements to, not replacements for, the manual recognition practice in Module 8's lab.

| Tool / project | What it does | Discipline it automates |
|---|---|---|
| **garak** | LLM vulnerability scanner — probes a model/prompt with attack sets (injection, jailbreaks, data leakage) and reports what passes | Module 8's attack categories, re-run per version (Module 10) |
| **PyRIT** (Microsoft) | Python framework for orchestrating red-team attacks and scoring responses at scale, built for agent/automation red-teaming | Multi-turn, multi-attack campaigns; reproducible attack logs |
| **Giskard** | Automated ML/LLM testing focused on Python repos; scans for vulnerabilities, hallucinations, and behavioral issues | Injection + quality regressions in CI |
| **Prompt-injection scanners bundled in eval frameworks** | Several evaluation frameworks (Section 2) ship red-team/attack datasets you can point at your own prompts | Re-running adversarial sets in the same pipeline as quality eval |

**Ground rule from Module 8:** automated scanners give breadth and a paper trail; they do not prove safety. A system passing a scanner can still fail under a novel, rephrased attack — treat scans as regression tests, not certifications.

---

## 2. Evaluation Frameworks (Module 9)

These implement the Module 9 pipeline: golden datasets, LLM-as-a-judge scoring, CI gates, and (often) A/B-style rollouts.

| Tool / project | What it does | Best fit |
|---|---|---|
| **promptfoo** | Open-source eval + red-team framework: dataset-driven testing, config-based, CLI/CI friendly, supports most providers and self-hosted models | Regression-testing prompt versions; comparing variants; integration with the Module 10 version loop |
| **OpenAI Evals** | Reference eval framework (registry of datasets + judge/eval logic); model-agnostic to a degree but OpenAI-leaning | Starting from a community eval registry |
| **LangSmith** | Tracing, datasets, and online evaluation across LLM app stacks | Debugging + monitoring a live app and sampling production evals (Module 9.4 production stage) |
| **DeepEval** | Pytest-style LLM evaluation with metrics (G-Eval, faithfulness, etc.) and CI integration | Teams that want evals as unit tests in an existing test suite |
| **Braintrust / Phoenix / Weave** | Evaluation + experimentation platforms with dataset management, judging, and experiment comparison | Comparing many experiment runs and versioning eval artifacts |

**Picking one:** the practical differentiators are (a) whether it integrates with your provider/self-hosted model, (b) whether it can run in your CI as a gate (Module 9.4), and (c) whether it versions the dataset, prompt, judge, and model the way Module 9.6 requires. Start with whichever is easiest to wire into your existing test pipeline — the concepts in Module 9 matter more than the specific tool.

---

## 3. Token Counting & Interface Tooling

| Tool / project | What it does | Where it helps |
|---|---|---|
| **tiktoken** | OpenAI's BPE tokenizer library | Counting tokens exactly (Module 1), budgeting prompts and max_tokens (Module 7) |
| **Provider playgrounds / API docs** | Interactive token counters and parameter controls | Hands-on temperature/top-p/seed experiments (Module 7 lab) |

---

## 4. Choosing Conventions

Whichever tools you pick, the Module 9/10 disciplines stay the same:

1. **Version the dataset, prompt, model, parameters, and judge** — a tool that can't record these loses its reproducibility value
2. **Gate in CI** — an eval that only runs locally reverts to a vibe check
3. **Feed production failures back** into your golden dataset — a tool without a feedback loop risks drifting out of reality
4. **Automate breadth, keep manual judgment** — scanners find what they're told to look for; your Module 8/9 judgment finds what they miss

---