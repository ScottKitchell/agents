# teach-me

Teaches a topic in small, conversational units aimed at the learner's next click of understanding, mixing plain language, analogy, visuals, domain terms, and examples only where they help. It runs only when the user explicitly invokes it.

## Why it exists

Agents explain by covering everything at once: long, encyclopaedic answers that overload newcomers and bore people who already know the basics. This skill teaches one meaningful idea at a time and adapts to what the learner shows they know. It is for rapid understanding, not curricula, quizzes, or quick fact lookups.

Design decisions, from research reviewed in September 2026:

- **One coherent unit at a time, paced by the learner.** Meaningful, learner-paced segments improve retention and transfer ([Rey et al.](https://doi.org/10.1007/s10648-018-9456-4); [How People Learn II](https://www.nationalacademies.org/read/24783/chapter/7)). Fixed sequences and fixed lengths were rejected.
- **More guidance for novices, less for experts** ([Tetzlaff et al.](https://doi.org/10.1016/j.learninstruc.2025.102142)).
- **Functional, labelled visuals** that point at the key relationship ([Richter et al.](https://doi.org/10.1016/j.edurev.2015.12.003)).
- **Engagement only when it carries the idea.** Interesting but irrelevant detail hinders learning ([Sundararajan and Adesope](https://doi.org/10.1007/s10648-020-09522-4)).
- **Analogies mapped back to the real domain**, because surface similarity doesn't transfer ([Loewenstein et al.](https://groups.psych.northwestern.edu/gentner/papers/LoewensteinThompsonGentner03.pdf)).
- **Key terms named just before they're needed** ([Mayer, pre-training](https://doi.org/10.1017/CBO9780511811678.014)).
- **Tiny checks are optional.** Retrieval aids retention ([Roediger and Karpicke](https://doi.org/10.1111/j.1467-9280.2006.01693.x)), but spacing and study programmes are out of scope.

## Iterating

- Check that a simple topic gets a one-beat answer and a complex one can expand naturally.
- Reject changes that turn the ingredient table into a mandatory workflow.
- The skill infers prior knowledge from conversation, not a formal assessment. Real usage examples are now worth more than further literature; collect them before adding behaviour.
