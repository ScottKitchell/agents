# expert-opinion

When the right approach is unclear, finds how experienced practitioners (in this field or others) already solve the problem, picks the best-supported approach, and keeps working. It loads automatically, including mid-task.

## Why it exists

Agents facing a trade-off either guess from training data or hand the user a menu of options. Neither is what an expert colleague does. This skill makes the agent research in proportion to the stakes, then decide and continue, asking the user only for private context, preferences, or authority that research can't supply.

Design choices:

- **Aim the search before running it.** Name the problem in the field's own terms, and choose the disciplines accountable for the outcome, not only those that share the task's medium.
- **Prefer what people built or ran, with results** (implementations, case studies, postmortems) over recommendations and vendor claims.
- **Proportionate research budget**, scaled by reversibility and blast radius, with a bias to stop once a small experiment would teach more than further reading.
- **Startup defaults** (speed, simplicity, limited people and money) reflect how I work. Large-company examples are mined for the lesson, not the machinery.
- **Brief borrowing from other domains** only when direct precedent is thin. A broad hunt for novel ideas is `creative-problem-solve`.

## Iterating

- Test mid-task: give an agent a build task with a real unresolved trade-off and check it researches, writes a short decision note with links, and continues without asking which option to choose.
- Test the near miss: a settled or trivial choice should not trigger a search.
