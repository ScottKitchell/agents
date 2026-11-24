# get-me-up-to-speed

Replaces `fast-track`. It's for the moment someone brings you a problem, asks for feedback on their work, or drops you into an area outside your domain, and you need to understand enough to join in. It also handles broad topics such as "the state of AI". It gauges your goal and starting point first, teaches only the gap along a short route of at most five stops, works top-down from the big picture, gives you the team's vocabulary, and makes every checkpoint an exit or a chance to go deeper. It teaches and never acts unless asked. It remains manual-only.

## Design decisions

Research reviewed on 24 November 2026, building on the instructional-design review done for `fast-track` on 17 November 2026.

| Evidence | Decision and boundary |
| --- | --- |
| [Ausubel, Educational Psychology: A Cognitive View](https://en.wikipedia.org/wiki/David_Ausubel) (1968): the most important factor in learning is what the learner already knows; ascertain it and teach accordingly. Advance organisers frame new material against prior knowledge, though [later reviews](https://link.springer.com/article/10.1007/s12144-023-04440-4) find the evidence mixed. | Gauge before teaching, teach only the diff, and open with a big-picture frame. Treat the organiser as a design heuristic, not a proven effect. |
| [Kalyuga et al., The Expertise Reversal Effect](https://www.davidlewisphd.com/courses/EDD8121/readings/2003-Kalyuga_et_al.pdf): guidance that helps novices can hinder knowledgeable learners. | Skip what the user knows; the same topic gets a different lesson for a newcomer and someone who is merely behind. |
| Diagnostic and [hinge questions](https://educationendowmentfoundation.org.uk/public/files/Diagnostic_Assessment_Tool.pdf) in formative assessment probe prior knowledge and misconceptions with a concrete question; a single question is a noisy signal. | Gauge with a concrete probe rather than self-rated familiarity, keep it to one short message, and keep adjusting as answers come in. |
| [BLUF](https://en.wikipedia.org/wiki/BLUF_(communication)) in military writing and [Minto's pyramid principle](https://lethain.com/pyramid-principle/) (situation, complication, question, then answer and supporting detail). [Garner](https://www.abajournal.com/columns/article/should-the-bottom-line-be-up-front-only-with-context-says-bryan-garner) notes BLUF assumes the reader already has context. | Teach top-down. Because the user lacks context, open with the situation and problem before descending, rather than a bare bottom line. |
| Practitioners ramping up on unfamiliar codebases ([GitHub](https://github.blog/developer-skills/application-development/how-github-engineers-learn-new-codebases), [Holloway](https://www.holloway.com/g/junior-to-senior/sections/dont-try-to-understand-it-all)) build a boxes-and-arrows model first and deliberately avoid understanding everything. | Map the main parts before detail; go low-level only where a detail is load-bearing for the job. |
| [LearnLM](https://arxiv.org/abs/2412.16429): default model "helpfulness" (presenting or doing) often conflicts with learning. | Teach only and leave action to an explicit request, so the skill doesn't slide into fixing the problem. |
| Merrill, Mayer segmenting, retrieval practice and CMU learning principles (see the `fast-track` history in git). | Keep chunked delivery, learner-steered checkpoints and occasional lightweight checks, scaled down for a goal of conversational readiness rather than mastery. |

Broad topics have no natural endpoint, so the lesson is bounded by the user's job (or a default working overview), a visible route of at most five stops, and an explicit "Stop here" at every checkpoint. The five-stop cap is a judgement, not a researched limit.

The checkpoint menu, the definition of "load-bearing" detail and the vocabulary step (borrowed from `concept-driven-design`) are design judgements, not tested protocols.

## Check changes

Validate frontmatter, matching folder/name and all three manual-only controls. Keep the repository index current. This repository is canonical; global installs update through the skills CLI after changes are pushed.

In fresh sessions, compare the same prompts with this skill explicitly loaded and without it:

- Paste a Slack thread where a colleague asks for help with a bug in an unfamiliar service. Expect gauging questions (or stated assumptions) before teaching, then situation → problem → the crux, with the team's terms in bold, and no proposed fix.
- "Get me up to speed on this PR so I can review it" with a link. Expect the purpose and shape of the change first, then only the details a reviewer needs, and open questions worth asking the author.
- "Get me up to speed on our data warehouse. I know SQL well." Expect familiar material skipped and depth on what's specific to this setup.
- "Get me up to speed on the state of AI." Expect a question about what you'll use it for, then a route of no more than five stops, a dated snapshot from current sources, and "Stop here" at every checkpoint.
- At a checkpoint, ask to go deeper, then to continue. Expect a one-stop detour and a clean return to the route. Choose "Stop here" early; expect a recap plus a line on what the remaining stops would have covered.
- Mid-lesson, say nothing about action. Expect no fixes, drafts or edits. Then ask it to fix the problem; expect it to switch to doing.

At a checkpoint, check that the next moves appear in the harness's question widget where one exists (Claude Code, and Codex or Cursor where their question tool is enabled), after the stop's content is fully written, and as lettered text elsewhere.

Check that ordinary explanation requests do not implicitly activate this manual-only workflow. Judge success by whether the user can explain the situation, use the vocabulary and contribute a sensible view in the real conversation, and by time spent.
