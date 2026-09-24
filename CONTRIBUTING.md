# Contributing to This Course

Thanks for helping improve the course materials. Every contribution that makes the modules clearer, more current, or more practical is welcome.

## Ways to Contribute

- **Fix errors** — typos, outdated figures (models, context windows, pricing, provider parameter names), or broken cross-references
- **Add examples** — live prompts, worked outputs, or scenario extensions for existing exercises
- **Create exercises** — new practice problems and challenges that follow the patterns in `course_reference/reusable_exercise_patterns.md`
- **Share tips and patterns** — additions to `course_reference/` (glossary, cheat sheet, tooling index, or new reference files)
- **Report issues or suggestions** — open an issue describing the problem or idea

## How to Make a Change

1. Clone or fork the repository
2. Create a branch for your change
3. Make a focused edit — one logical change per contribution if possible
4. For substantive changes, note them in your commit message so it's easy to review
5. Open a pull request

## Conventions to Follow

- **Match the existing style** — the course uses the exact headers seen in the modules (`## N.N`, "Key Takeaways", mermaid diagrams with the same class-color palette). Mimic neighboring files rather than introducing a new format.
- **Keep it model-agnostic where possible** — the course deliberately avoids depending on a single provider. Where you cite specific models or parameter names, add a "verify against your provider's docs" note (the landscape changes quickly).
- **Security exercises stay fictional** — Module 8 materials must remain recognition-and-mitigation practice against fictional targets only. Never add real exploit code.
- **Don't add answer keys without discussion** — this course intentionally ships prompts/exercises without a public answer key; propose answer materials in an issue first.
- **No secrets** — never commit real credentials, API keys, or internal system prompts.

## Reviewing a Change

Substantive changes (new sections, renumbered content, new files) should reference the affected modules and update `course_structure.md` and `README.md` if the file layout changes. If you added a term, add it to `course_reference/glossary.md`; if you added tooling, consider `course_reference/tooling.md`.