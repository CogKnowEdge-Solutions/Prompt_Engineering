# Course Folder Structure

```
Prompt_Engineering/
├── README.md                    # Main course overview
├── course_structure.md          # This file
│
├── course_reference/                     # Course-wide reference
│   └── reusable_exercise_patterns.md     # Exercise formats used across all modules
│
├── module1/                     # Module 1: Foundations
│   ├── QUICK_START.md           # Fast entry point (Module 1 only)
│   ├── concepts.md              # Lesson notes
│   ├── lab.md                   # Lab activity
│   └── exercises_and_challenges.md       # Practice + challenge
│
├── module2/                     # Module 2: Prompting Techniques Taxonomy
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module3/                     # Module 3: Clarity, Structure & Few-Shot
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module4/                     # Module 4: Reasoning Techniques
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module5/                     # Module 5: Role & Context Setting
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module6/                     # Module 6: Output Control & Structured Data
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module7/                     # Module 7: Hyperparameters & Model Configuration
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module8/                     # Module 8: Prompt Security — Injection & Jailbreaking
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module9/                     # Module 9: Prompt Evaluation
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
├── module10/                    # Module 10: Iteration Workflow
│   ├── concepts.md
│   ├── lab.md
│   └── exercises_and_challenges.md
│
└── module11/                    # Module 11: Capstone Project (deliverable-based)
    ├── overview.md              # The four deliverables at a glance
    ├── track_options.md         # Track A / B / C or propose your own
    ├── deliverable_requirements.md      # Detailed per-deliverable requirements
    └── submission_checklist.md  # Self-review checklist and grading rubric
```

## File Descriptions

### Root Level
- **README.md**: Main course overview, structure, and getting started guide
- **course_structure.md**: This file showing the folder layout

### Course Reference (`course_reference/`)
- **reusable_exercise_patterns.md**: The recurring exercise formats (Fill-in-the-Pattern, Fix-the-Prompt, Before/After Comparison, Constraint Challenge, Red-Team/Patch Pair, Rubric Scoring, From Scratch) with what each tests and where it's used.

### Module Level (Modules 1-10)
- **concepts.md**: Lesson notes and Key Takeaways for the module
- **lab.md**: Hands-on activity practicing the module's skills
- **exercises_and_challenges.md**: Practice problems plus an advanced challenge
- **QUICK_START.md** (Module 1 only): Fast entry point for newcomers

### Capstone Level (Module 11)
- **overview.md**: Capstone structure, deliverables mapped to course modules, process diagram
- **track_options.md**: Track A (Customer Support), Track B (Content Generator), Track C (Coding Helper), or propose your own
- **deliverable_requirements.md**: Detailed checklists for deliverables D1-D4 (prompt system, eval report, red-team report, presentation)
- **submission_checklist.md**: Pre-submission self-review, 100-point grading rubric, suggested submission layout

## Course Progression

### Module 1: Foundations
- **Goal**: Understand how LLMs process prompts
- **Activities**: Compare vague vs. specific prompts
- **Skills**: Basic prompt writing, identifying common mistakes

### Module 2: Prompting Techniques Taxonomy
- **Goal**: Survey the full toolbox of prompting techniques
- **Activities**: Zero-shot, few-shot, CoT, role-based, self-consistency, ReAct, ToT, meta-prompting
- **Skills**: Recognizing techniques; choosing and combining them

### Module 3: Clarity, Structure & Few-Shot
- **Goal**: Write unambiguous prompts with strong examples
- **Activities**: Delimiters, XML tags, few-shot example design
- **Skills**: Structured prompting, example curation

### Module 4: Reasoning Techniques
- **Goal**: Elicit reliable multi-step reasoning from the model
- **Activities**: CoT, self-consistency, tree-of-thought, least-to-most
- **Skills**: Applying and choosing reasoning techniques

### Module 5: Role & Context Setting
- **Goal**: Use roles and context deliberately
- **Activities**: Role prompting experiments, over-trust risk analysis
- **Skills**: Role design, context setting, knowing when to skip personas

### Module 6: Output Control & Structured Data
- **Goal**: Get machine-usable structured output
- **Activities**: Schema-first prompting, JSON mode, few-shot extraction
- **Skills**: Schema design, handling missing/ambiguous data

### Module 7: Hyperparameters & Model Configuration
- **Goal**: Configure sampling and model settings deliberately
- **Activities**: Temperature/top-p, length & repetition controls
- **Skills**: Justifying hyperparameter choices, reproducibility, cost thinking

### Module 8: Prompt Security — Injection & Jailbreaking
- **Goal**: Understand and defend against prompt attacks
- **Activities**: Direct/indirect injection tests, escalation handling, defensive patterns
- **Skills**: Red-teaming, patching, threat modeling

### Module 9: Prompt Evaluation
- **Goal**: Prove a prompt works rather than assume it does
- **Activities**: Golden datasets, rubric scoring, LLM-as-a-judge
- **Skills**: Evaluation design, calibration, failure-pattern analysis

### Module 10: Iteration Workflow
- **Goal**: Manage prompts as versioned artifacts with a real process
- **Activities**: Iteration loop, rollback, staged deployment
- **Skills**: Versioning, hypothesis-driven change, process discipline

### Module 11: Capstone Project
- **Goal**: Integrate everything into one complete, evaluated, red-teamed prompt system
- **Activities**: Track A/B/C project with four deliverables (prompt system, eval report, red-team report, presentation)
- **Skills**: Synthesis — designing, measuring, and securing a full system

## Usage Tips

### For Learning:
1. Follow modules in order (1 → 11)
2. Complete all activities in each module
3. Attempt challenges and evaluations before looking at any model suggestions
4. Use `course_reference/reusable_exercise_patterns.md` to understand what each exercise type is testing

### For Teaching:
1. Use module concepts files as lecture outlines
2. Assign labs as in-class activities
3. Use exercises for homework
4. Use challenges for assessments
5. Use the Module 11 rubric (`submission_checklist.md`) for capstone grading

### For Practice:
1. Start with Module 1 if you're new to prompt engineering
2. Jump to specific modules based on your needs
3. Use the course reference to spot which skill each exercise targets
4. Create your own examples using the exercise pattern templates