# Teach Me Specification

## Intent

Help a learner gain useful understanding quickly through small, engaging, domain-grounded teaching beats. The skill should feel conversational and adaptive rather than like a fixed lesson plan.

## Scope

In scope:
- first exposure to a topic
- intuitive explanations and mental models
- deeper follow-up teaching driven by the learner
- engineering, product, business, and general domains

Out of scope:
- comprehensive curricula or study plans unless requested
- assessment-heavy tutoring by default
- terse fact lookup

## Users And Trigger Context

- Primary users: people explicitly asking the agent to teach them a topic
- Common requests: “teach me”, “help me understand”, “give me an intuitive picture”
- Should not trigger for: ordinary questions where the skill was not explicitly invoked

## Runtime Contract

- Optimize each response for the learner's next click of understanding.
- Use the smallest coherent teaching unit; do not impose a fixed sequence or length.
- Blend analogy, visuals, terminology, examples, and checks only as useful.
- Ground intuition in the real domain and adapt support to demonstrated prior knowledge.
- Keep engagement relevant to the concept.

## Source And Evidence Model

- Research provenance and decisions live in `SOURCES.md`.
- Favor authoritative syntheses, meta-analyses, and primary studies.
- Treat learning principles as context-sensitive guidance, not universal scripts.

## Reference Architecture

- `SKILL.md` contains all runtime guidance.
- `SPEC.md` defines the maintenance contract.
- `SOURCES.md` records evidence, decisions, limitations, and gaps.
- No runtime references or scripts are currently needed.

## Validation

- Validate frontmatter, name, portability, and referenced files.
- Review whether simple topics can produce a one-beat answer and complex topics can expand fluidly.
- Reject revisions that turn the ingredient palette into a mandatory workflow.

## Known Limitations

- The skill adapts from conversational cues rather than a formal prior-knowledge assessment.
- Effectiveness still depends on the agent's domain knowledge and choice of representation.

## Maintenance Notes

- Update `SKILL.md` only for behavior that should change on every invocation.
- Update `SOURCES.md` when evidence or a design decision changes.
