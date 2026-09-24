# Prompt Engineering Glossary

*A course-wide reference — the terms used across Modules 1-11, each with the module where it's covered in depth.*

---

## A

**A/B testing (Module 9)** — Running two prompt variants concurrently on live traffic and comparing real outcome metrics, rather than only offline judge scores.

---

## B

**Before/After Comparison (course reference)** — An exercise pattern: apply one technique to a prompt, run both versions, and attribute the change.

---

## C

**Canary release (Module 9)** — Rolling a change out to a small percentage of traffic first, watching for regressions, and expanding only once it's proven safe.

**Chain-of-Thought (CoT) (Modules 2, 4)** — Asking the model to reason step by step before giving its final answer, improving accuracy on multi-step tasks at a token cost.

**Context window (Module 1)** — The maximum number of tokens a model can process in one interaction (input + output combined).

---

## D

**Direct prompt injection (Module 8)** — A user types an instruction meant to override the system's original instructions.

**Drift (Module 9)** — A score change for no obvious reason: *output drift* (the model changed underneath you) or *input drift* (real traffic changed your assumptions).

---

## E

**Effective context (Module 1)** — The portion of an advertised context window a model actually uses well (typically ~50-65%).

---

## F

**Few-shot prompting (Modules 2, 3)** — Adding a few input→output examples to the prompt so the model copies the demonstrated pattern (in-context learning).

**Frequency penalty (Module 7)** — Discourages repetition by scaling with how often a token has already appeared.

**Function / tool calling (Module 6)** — An API-level structured-output path where the model returns a call to a registered function (name + arguments) rather than free text.

---

## G

**Golden dataset (Module 9)** — A set of input examples with known-good expected outputs, used to test a prompt consistently across changes. Best built from real failures.

---

## H

**Hallucination (Module 1)** — Plausible-sounding but false output; mitigated by verification, sources, and allowing "I don't know".

**Human-in-the-loop (HITL) (Module 8)** — Requiring a human confirmation step before consequential actions execute.

---

## I

**In-context learning (Module 2)** — The model learning a task pattern from examples inside the prompt, without retraining.

**Indirect prompt injection (Module 8)** — Malicious instructions hidden inside content the model retrieves or processes (webpage, document, email, tool output) — the more dangerous form in practice.

**Instruction hierarchy (Module 8)** — Structurally distinguishing trusted system instructions from untrusted content so they aren't treated as equally authoritative.

---

## J

**Jailbreaking (Module 8)** — Techniques for getting a model to bypass its safety guidelines, falling into recurring categories: reframing, gradual erosion, obfuscation, authority framing.

**JSON mode (Module 6)** — An API setting guaranteeing syntactically valid JSON output (but *any* shape, not necessarily the one you asked for).

**Judge (LLM-as-a-judge) (Module 9)** — A capable LLM scoring another model's output against a rubric; must be calibrated against human labels (~85-90% agreement) before being trusted.

---

## L

**Least-to-most prompting (Module 4)** — Breaking a complex problem into ordered sub-problems solved sequentially, reusing each answer.

**Least privilege (Module 8)** — Giving an agent/assistant only the tools, data, and permissions its task requires, to limit blast radius when an injection succeeds.

**Lexical tokens → see Tokens.**

**Logit bias (Module 7)** — Nudging the likelihood of specific tokens up or down (a scalpel compared to temperature's broad brush).

---

## M

**Max tokens (Module 7)** — A hard ceiling on response length; directly controls cost and prevents runaway generation.

**Meta-prompting (Module 2)** — Using prompts to generate or optimize other prompts; also the foundation of automated prompt-optimization methods.

---

## P

**Persona / Role prompting (Modules 2, 5)** — Assigning the model a role to steer vocabulary, tone, and emphasis. Evidence shows it changes style more reliably than accuracy.

**Presence penalty (Module 7)** — A flat penalty once a token has appeared at all, nudging the model toward new topics.

**Prompt caching (Module 7)** — Reusing a processed prefix across calls to cut cost; sensitive to exact config (silently breaking on cache-miss).

---

## R

**RAG (Retrieval-Augmented Generation) (Module 2)** — Combining a prompt with retrieved relevant documents to reduce hallucination and ground answers.

**ReAct (Modules 2, 8)** — Reasoning + Acting: interleaving thoughts and tool actions.

**Reasoning effort / thinking tokens (Module 7)** — How much internal reasoning a model does before its visible answer; higher effort = more tokens/latency, not automatically better.

**Red teaming (Module 8)** — Attempting to break a system's prompt (attack categories), then patching and re-testing.

---

## S

**Sanity checks (Module 9)** — Fast, deterministic, unit-test-style checks (parses? allowed label? required fields?) run before expensive judged evaluation.

**Schema-first prompting (Module 6)** — Showing the exact output shape in the prompt before the input content.

**Seed (Module 7)** — A setting that makes output *more* reproducible (best-effort, not a guarantee).

**Self-consistency (Modules 2, 4)** — Running the same prompt multiple times and taking the majority answer; filters random errors, not systematic ones.

**Stop sequence (Module 7)** — A string that halts generation the moment it appears, cutting output at a boundary.

**Structured outputs / schema enforcement (Module 6)** — An API feature constraining each generated token to match a schema you supply; stronger than JSON mode and than prompting alone.

**Sycophancy (Module 1)** — The model's tendency to agree with the user even when wrong.

**System prompt (Module 1)** — Persistence instructions setting role, behavior, and constraints across all interactions.

---

## T

**Temperature (Modules 1, 7)** — The master randomness dial; sharpens or flattens the next-token probability distribution. Not a correctness knob — even 0.0 isn't byte-deterministic.

**Tokens (Module 1)** — The basic units LLMs process; roughly a word, but rare words and code can cost several.

**top-k (Module 7)** — Caps the candidate pool to a fixed number of the most likely tokens.

**top-p / nucleus sampling (Module 7)** — Keeps the smallest set of tokens whose combined probability crosses a threshold, sampling from that set only.

**Tree-of-Thought (ToT) (Modules 2, 4)** — Branching into multiple reasoning paths, pruning weak branches, exploring the strongest — the most token-expensive reasoning technique.

---

## Z

**Zero-shot prompting (Module 2)** — An instruction with no examples; the model relies on what it already knows.

---