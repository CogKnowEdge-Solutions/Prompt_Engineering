# Prompt Engineering Course

## Course Overview
A comprehensive course on mastering the art and science of prompt engineering for Large Language Models (LLMs) — from foundational prompting through advanced techniques, structured output, security, evaluation, iteration workflow, and a capstone project.

## Course Structure

### Module 1: Foundations
**Folder:** `module1/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`, `QUICK_START.md`
**Topics:**
- What is Prompt Engineering? How LLMs process prompts
- Prompt structure template and common pitfalls
- Lab: Compare outputs from vague vs. specific prompts
- Exercises: Fill-in-the-pattern, Fix-the-prompt

### Module 2: Prompting Techniques Taxonomy
**Folder:** `module2/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- Zero-shot, few-shot, and chain-of-thought (CoT) prompting
- Role/persona prompting, self-consistency, ReAct, tree-of-thought, meta-prompting
- Choosing and combining techniques

### Module 3: Clarity, Structure & Few-Shot
**Folder:** `module3/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- Delimiters and XML tags, when structure doesn't help
- Designing good few-shot examples, structure + examples together

### Module 4: Reasoning Techniques
**Folder:** `module4/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- CoT revisited, self-consistency, tree-of-thought, least-to-most
- Choosing the right reasoning technique

### Module 5: Role & Context Setting
**Folder:** `module5/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- How role prompting works, the mixed research, over-trust risk
- Practical guidelines for roles, context beyond roles, when to skip the persona

### Module 6: Output Control & Structured Data
**Folder:** `module6/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- Schema-first prompting, JSON mode / structured outputs
- Few-shot for extraction, handling missing or ambiguous data

### Module 7: Hyperparameters & Model Configuration
**Folder:** `module7/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- Randomness/sampling, length & repetition controls
- Reproducibility, performance & cost, putting it together

### Module 8: Prompt Security — Injection & Jailbreaking
**Folder:** `module8/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- Direct vs. indirect injection, the full threat landscape
- Case studies (EchoLeak, GitHub Copilot) — defensive design patterns

### Module 9: Prompt Evaluation
**Folder:** `module9/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- Golden datasets, LLM-as-a-judge, production evaluation pipeline
- A/B testing, reproducibility, metrics that matter

### Module 10: Iteration Workflow
**Folder:** `module10/`
**Files:** `concepts.md`, `lab.md`, `exercises_and_challenges.md`
**Topics:**
- Prompts as versioned artifacts, staged deployment
- Tying in evaluation (M9) and security (M8), a practical iteration loop

### Module 11: Capstone Project
**Folder:** `module11/`
**Files:** `overview.md`, `track_options.md`, `deliverable_requirements.md`, `submission_checklist.md`
**Topics:**
- Build one complete prompt system end-to-end (pick a track or propose your own)
- Four deliverables: full prompt system, eval report, red-team report, presentation/review

### Course Reference
**Folder:** `course_reference/`
**Files:** `reusable_exercise_patterns.md`
**Purpose:** The recurring exercise formats used across all modules, and what each one actually tests.

## How to Use This Course

### For Self-Learners:
1. Start with Module 1 and work sequentially
2. Complete all labs and exercises
3. Attempt challenges before checking your reasoning against the prompts
4. Finish with the Module 11 capstone to integrate everything

### For Instructors:
1. Use module folders as lecture materials
2. Assign exercises as homework
3. Use challenges for assessments
4. Use the Module 11 capstone deliverables as a final assessment

## Prerequisites
- Basic computer literacy
- Access to an LLM (ChatGPT, Claude, Gemini, etc.)
- No programming experience required (the Module 11 capstone's Coding Helper track involves reading code snippets)

## Learning Outcomes
By the end of this course, you will be able to:
- [ ] Understand how LLMs process and respond to prompts
- [ ] Write clear, specific, and effective prompts
- [ ] Apply advanced prompting techniques (reasoning, roles, structure)
- [ ] Control output format with structured data and schemas
- [ ] Configure hyperparameters for reliability, cost, and reproducibility
- [ ] Red-team prompts against injection and jailbreak attacks
- [ ] Evaluate prompt quality with datasets, rubrics, and judges
- [ ] Run a disciplined iteration workflow with versioned prompts
- [ ] Build and document a complete, shippable prompt system

## Course Materials
Each module (1-10) contains:
- **concepts.md**: Lesson notes for the module
- **lab.md**: Hands-on activity
- **exercises_and_challenges.md**: Practice problems + advanced challenge
- **QUICK_START.md** (Module 1 only): Fast entry point

The capstone (`module11/`) uses a project structure instead:
- **overview.md**: The four deliverables at a glance
- **track_options.md**: Track A / B / C or propose your own
- **deliverable_requirements.md**: Detailed per-deliverable requirements
- **submission_checklist.md**: Self-review checklist and grading rubric

## Getting Started
1. Clone or download this repository
2. Start with `module1/QUICK_START.md` (then `module1/concepts.md`)
3. Follow the module structure in order
4. Complete all activities, then finish with the Module 11 capstone

## Contributing
Feel free to improve the course materials:
- Add more examples
- Create additional exercises
- Share your prompt engineering tips
- Report issues or suggestions

## License
This course is for educational purposes. Use and adapt as needed for your learning or teaching.

## Support
If you have questions about the course content:
- Review the module concepts files
- Check the course reference for exercise patterns
- Practice with additional examples
- Join prompt engineering communities for discussion