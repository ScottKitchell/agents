# fast-track

Replaces `teach-me` with a guided route to a concrete capability: broad orientation, essential foundations, application and the complexity that changes outcomes. It remains manual-only. The running example connects the sections; checkpoints let the learner steer without having to design their own curriculum.

## Design decisions

Research reviewed on 17 November 2026 spans instructional design, cognitive psychology, multimedia learning and university teaching practice.

| Evidence | Decision and boundary |
| --- | --- |
| [Merrill, First Principles of Instruction](https://mdavidmerrill.files.wordpress.com/2019/04/firstprinciplesbymerrill.pdf) synthesises task-centred instruction, activation, demonstration, application and integration. | Start with a meaningful whole and build towards using it. This is a design framework, not experimental proof of this skill. |
| [Van Merriënboer and colleagues, Ten Steps to Complex Learning](https://research.ou.nl/ws/portalfiles/portal/941352/Ten%20Steps%20to%20Complex%20Learning%20-%20Sage%2021st%20Century.pdf) describe whole tasks, increasing difficulty, variability and diminishing support. | Use a running problem and progressively harder cases. Borrow the mechanism without importing a full course-design process. |
| [Kalyuga et al., The Expertise Reversal Effect](https://www.davidlewisphd.com/courses/EDD8121/readings/2003-Kalyuga_et_al.pdf) reviews how guidance useful to novices can become redundant for knowledgeable learners. | Show reasoning early, then fade it in response to demonstrated understanding. A fixed beginner sequence would waste experienced learners' time. |
| [Mayer, Segmenting, Pretraining and Modality Principles](https://doi.org/10.1017/CBO9780511816819.012) reports experimental support for learner-paced multimedia segments and knowing key components before complex explanations. | Pause at conceptual boundaries and establish essential names and roles. Findings about narrated multimedia do not establish a universal best medium for chat. |
| [Karpicke and Blunt, retrieval practice](https://pubmed.ncbi.nlm.nih.gov/21252317/) found benefits for conceptual science learning, including comprehension and inference. | Include brief attempts to retrieve and apply ideas, with feedback. Reading fluency and self-reported confidence do not establish learning. |
| [Carnegie Mellon's learning principles](https://www.cmu.edu/teaching/principles/learning.html) synthesise prior knowledge, knowledge organisation, integrated skills and targeted practice with feedback. | Adapt the route to the learner and verify the target capability through an integrated application. |

The specific checkpoint menu, running-example default and “useful understanding per minute” objective are design judgements, not a tested optimal tutoring protocol. Most evidence comes from structured educational settings, not general-purpose conversational agents. Validate retention and transfer through use before claiming this implementation accelerates learning.

## Check changes

Validate frontmatter, matching folder/name and all three manual-only controls. Keep the repository index current. This repository is canonical; global installs update through the skills CLI after changes are pushed.

In fresh sessions, compare the same prompts with this skill explicitly loaded and without it:

- “Fast-track me on databases. I have 15 minutes and need to choose one for an app.” Expect a concrete decision capability, a short route, a useful first foundation and a checkpoint before the full journey.
- “Fast-track me on compound interest from scratch.” Expect a simple numerical example that develops into compounding, time and consequential assumptions, using a chart or calculator if worthwhile.
- “Fast-track me on distributed systems. I know databases and HTTP.” Expect familiar material compressed and depth focused on interactions and failure modes.
- At a checkpoint, give a wrong prediction, ask for depth, then ask to resume. Expect a targeted repair, a bounded detour and a coherent return, preserving the running example.
- “Fast-track me on what idempotent means.” Expect one compact explanation rather than an inflated curriculum. “Skip the exercises” must preserve learner control without a mastery claim.

Check that ordinary explanation requests, fact lookups and requests to draft a training document do not implicitly activate this manual-only workflow. Evaluate the learner's ability to explain or solve an unfamiliar case, time spent, continuity and delayed recall where practical. An attractive lesson and a passed format check do not demonstrate learning effectiveness.
