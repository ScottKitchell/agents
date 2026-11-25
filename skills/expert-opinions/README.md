# expert-opinions

When the right approach is unclear, finds how experienced practitioners (in this field or others) already solve the problem, picks the best-supported approach, and keeps working. It loads automatically, including mid-task.

## Why it exists

Agents facing a trade-off either guess from training data or hand the user a menu of options. Neither is what an expert colleague does. This skill makes the agent research in proportion to the stakes, then decide and continue, asking the user only for private context, preferences, or authority that research can't supply.

Design choices:

- **Aim the search before running it.** Write the problem's domain-free shape, then shortlist named references before reading anything. Selection is where a plain "research this first" prompt fails: it finds the nearest blog post, not the best solver.
- **Three levels of abstraction, one scale.** Same problem, same purpose, same shape. Each holds less of the problem constant and does a different job: level 1 solves the obvious efficiently, level 2 explains why things work, level 3 sharpens the problem and finds the strongest mechanism anywhere. Moving up the scale often makes the problem better defined, not stranger, which is why the shape line is always written. Design-by-analogy research is consistent with starting concrete: distant sources gave more novel but less immediately usable ideas, and distance can go too far (Fu et al. 2013; Franke, Poetz and Schreier 2014). Neither study sets an allocation, so the skill gives widening conditions rather than percentages.
- **Pressure finds sources; outcomes judge them.** Stakes, reps and feedback point to where practice has been tested. Whether it works is judged by the observed outcome, the independence of examples, and what made it viable there.
- **A reference is a solution plus its makers' reasoning.** Neither is proof alone: write-ups are filtered by hindsight, survivorship, novelty and incentives, and behaviour by switching costs and copied defaults. Evidence against the source's interest (reversals, failure write-ups) is hardest to fake.
- **Counter the agent's own bias.** On material decisions it seeks people who abandoned the leading approach and the strongest case against its favoured option, so it doesn't anchor on the first result or the user's hint.
- **The decision sets the depth.** Effort scales with reversibility and blast radius, and the search widens beyond level 1 only when the shape line or level 1 results suggest it could change the call. Stop once a small experiment would teach more than further reading.
- **Level 3 stays deep but narrow.** A broad hunt for novel ideas is `creative-problem-solve`.

## Iterating

- Test mid-task: give an agent a build task with a real unresolved trade-off and check it researches, writes a short decision note with links, and continues without asking which option to choose.
- Test depth: a material choice that docs and a local precedent settle (such as a retry policy for a new integration) should stop at level 1 with a written shape line. A choice where level 1 sources all ship the same mediocre answer should widen, with a level 3 domain chosen for stakes, reps and feedback.
- Test the near miss: a settled or trivial choice should not trigger a search.
