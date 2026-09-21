# Teach Me Sources

Research reviewed on 2026-09-21.

## Source Inventory

| Source | Trust | Contribution |
|---|---|---|
| [How People Learn II, Chapter 5](https://www.nationalacademies.org/read/24783/chapter/7) | Authoritative synthesis | Novices need structures that help integrate knowledge; useful strategies depend on prior knowledge, material, context, and goals. |
| [Rey et al., A Meta-analysis of the Segmenting Effect](https://doi.org/10.1007/s10648-018-9456-4) | Peer-reviewed meta-analysis | Meaningful, learner-paced segments improve retention and transfer and reduce cognitive load; segmentation is not an arbitrary word limit. |
| [Tetzlaff et al., A cornerstone of adaptivity](https://doi.org/10.1016/j.learninstruc.2025.102142) | Peer-reviewed meta-analysis | Novices tend to benefit from more assistance while knowledgeable learners tend to benefit from less; effects vary by context. |
| [Richter, Scheiter, and Eitel, Signaling text-picture relations](https://doi.org/10.1016/j.edurev.2015.12.003) | Peer-reviewed meta-analysis | Visual cues that expose text-picture relationships aid comprehension, especially when visual search is demanding. |
| [Sundararajan and Adesope, Keep It Coherent](https://doi.org/10.1007/s10648-020-09522-4) | Peer-reviewed meta-analysis | Interesting but irrelevant details can hinder learning, so engagement should serve the mental model. |
| [Loewenstein, Thompson, and Gentner, Learning and Transfer](https://groups.psych.northwestern.edu/gentner/papers/LoewensteinThompsonGentner03.pdf) | Peer-reviewed primary research | Analogical comparison helps learners extract relational structure; surface similarity alone does not reliably transfer. |
| [Mayer, Pre-training Principle](https://doi.org/10.1017/CBO9780511811678.014) | Research synthesis with cited experiments | Naming the key parts of a complex system before their interactions can reduce competing processing demands. |
| [Roediger and Karpicke, Test-Enhanced Learning](https://doi.org/10.1111/j.1467-9280.2006.01693.x) | Peer-reviewed primary research | Retrieval can strengthen later retention; retained only as an optional tiny check because this skill prioritizes immediate understanding. |
| [Agent Skills specification](https://agentskills.io/specification) | Normative format | Keeps the runtime skill portable and limited to standard frontmatter plus Markdown. |

## Decisions

| Status | Decision | Evidence |
|---|---|---|
| Adopted | Teach one meaningful unit at a time and let the learner control continuation. | Segmenting meta-analysis; How People Learn II |
| Adopted | Make visuals functional, labeled, and focused on the important relationship. | Signaling and coherence evidence |
| Adopted | Explicitly map analogies back to domain structure. | Analogical encoding research |
| Adopted | Increase guidance for novices and fade it when prior knowledge is evident. | Expertise-reversal meta-analysis |
| Adopted | Use key terminology just before it becomes necessary in a complex explanation. | Pre-training evidence |
| Rejected | A mandatory multi-step teaching sequence. | Conflicts with context-sensitive and adaptive evidence |
| Rejected | Arbitrary chunk lengths or a fixed response size. | Segment coherence matters more than a universal size |
| Rejected | Decorative visuals, stories, or enthusiasm detached from the concept. | Seductive-details evidence |
| Deferred | Retrieval schedules, spacing, and full study-program design. | Valuable for retention but outside the skill's rapid-understanding focus |

## Coverage And Gaps

| Dimension | Status |
|---|---|
| novice entry and mental models | covered |
| meaningful chunking and pacing | covered |
| visuals and attention guidance | covered |
| analogy and domain transfer | covered |
| prior-knowledge adaptation | covered |
| relevant engagement | covered |
| long-term retention curriculum | intentionally out of scope |
| behavioral examples and holdout evaluations | open; add after observing real use |

## Adaptation Notes

- Source intent preserved: manage cognitive load, form coherent mental models, and support transfer.
- Local target: short conversational explanations rather than courses or multimedia modules.
- Research principles were translated into flexible decisions, not copied as a prescribed lesson format.
- Provider-specific activation metadata was omitted for portability; explicit invocation remains part of the description contract.

## Stopping Rationale

The source set covers the requested high-impact dimensions with authoritative synthesis, meta-analysis, and primary evidence. Further retrieval was becoming repetitive; real usage examples are now more valuable than additional general literature.
