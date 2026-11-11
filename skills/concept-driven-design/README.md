# concept-driven-design

Applies Concept-Driven Design (CDD) to software work: find the named concepts a change touches, keep each one holding, distinct, and fitting, and make code, product, tests, and vocabulary tell one story. It loads automatically for planning, building, and reviewing, scaled down to a silent check for small changes.

## Why it exists

Agents add special cases, synonyms, and new nouns instead of asking whether an existing concept is wrong. Over many changes the implementation drifts from what things mean, and the system gets heavy to work with. This skill makes protecting **conceptual integrity** part of every change.

The full write-up of CDD, and draft posts about it, live in [`concept-driven-design/`](../../concept-driven-design/) at the repo root. It turns Fred Brooks's conceptual integrity into day-to-day practice, and sits alongside Domain-Driven Design as a thinner, broader cousin that also covers UI and code outline.

## Layout

- `SKILL.md`: vocabulary, the three integrity tests, and the workflow.
- `references/architecture.md`, `code.md`, `product.md`: how CDD applies to each kind of work, with smells to look for.

## Iterating

- Test with a small bug fix (should stay silent unless it finds drift), a feature (should name the concepts touched before coding), and a new subsystem (should propose a concept map first).
- Keep the skill and the long-form write-up consistent. When the method changes, update the write-up first, then the skill.
