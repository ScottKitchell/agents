# expert-opinion

When the right approach is unclear, finds how experienced practitioners (in this field or others) already solve the problem, picks the best-supported approach, and keeps working. It loads automatically, including mid-task.

## Why it exists

Agents facing a trade-off either guess from training data or hand the user a menu of options. Neither is what an expert colleague does. This skill makes the agent research in proportion to the stakes, then decide and continue, asking the user only for private context, preferences, or authority that research can't supply.

Design choices:

- **Aim the search before running it.** Name the problem in the field's own terms and as a domain-free structure, then shortlist named references before reading anything. Selection is where a plain "research this first" prompt fails: it finds the nearest blog post, not the best-fitting precedent.
- **Three rings of distance.** Near (same problem, same context) is most actionable; mid (people who do the underlying job, or own the outcome elsewhere) explains why things work; far (same structure, different problem) yields differentiating mechanisms. Research on design-by-analogy points the same way: near and middle-distance sources produce the most useful ideas, far sources the most novel but least feasible (Fu et al. 2013; Franke, Poetz and Schreier 2014). Hence the default of mostly near, some mid, a little far, shifted by what the opinion is for.
- **Prefer what people built or ran, with results** (implementations, case studies, postmortems) over recommendations and vendor claims.
- **Proportionate research budget**, scaled by reversibility and blast radius, which also sets how many rings to cover. Stop once a small experiment would teach more than further reading.
- **The far ring stays brief.** A broad hunt for novel ideas is `creative-problem-solve`.

## Iterating

- Test mid-task: give an agent a build task with a real unresolved trade-off and check it researches, writes a short decision note with links, and continues without asking which option to choose.
- Test ring selection: give a material feature decision and check the note names specific near and mid references, and a far one only when near precedent is thin or uniform. A small reversible choice should stay near.
- Test the near miss: a settled or trivial choice should not trigger a search.
