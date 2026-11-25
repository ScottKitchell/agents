---
name: expert-opinions
description: Finds how experienced practitioners, in this field and others, already solve a problem, then picks an approach and keeps working. Use proactively when the right approach is unclear or a design, technical, product, process, or strategy trade-off is unresolved, including mid-task. Not for settled choices or open-ended brainstorming.
metadata:
  author: ScottKitchell
---

# Expert Opinion

Borrow judgement from people who have already solved this problem, or one shaped like it, then decide and carry on with the user's task.

## Frame the decision

State the decision and what success looks like. Research and make the expert judgement yourself: what works, under which conditions, at what cost. Ask the user only for what research can't supply: private context, taste, or the intended outcome when it is genuinely ambiguous. Check the task context and connected sources first; then ask narrowly, say why it matters, and recommend an answer. Never ask the user to choose between approaches they have no particular reason to know. Respect explicit user choices and existing project concepts, and reopen a settled decision only on material new evidence.

## Search across three levels of abstraction

Learn from **references**: a solution plus the reasoning of the people who built it. They sit at three levels of abstraction. Each level holds less of the user's problem constant and does a different job:

| Level | Held constant | Test for a candidate | What it gives |
| --- | --- | --- | --- |
| 1. Same problem | The problem and its context: users, product type, medium, constraints | Could you largely copy it and adapt the details? | The obvious, solved efficiently: patterns, pitfalls, conventions users expect |
| 2. Same purpose | The outcome sought, pursued by people doing the job directly or by other disciplines accountable for it | Are they producing the same result for people, by other means? | Why things work and what the job really needs |
| 3. Same shape | Only the core structure; purpose and setting differ | Does their problem fit the user's problem stated in one domain-free line? | A sharper definition of the problem, and the strongest mechanism, wherever it lives |

For example, deciding when to send push notifications:

1. Other consumer apps' notification strategies and opt-out data.
2. Lifecycle marketers and behavioural scientists on what brings people back.
3. "Interrupt someone only when it's worth it, or they learn to ignore you" leads to clinical **alarm fatigue** research: tiered urgency, suppressed duplicates, tuned thresholds.

Always write the one-line shape, even for a small decision: it is how you tell whether searching beyond level 1 could change the call. Name the problem for each level you search in that level's terms: the field's, the outcome's, or the shape's established name.

## Set the search depth

Scale the search with the cost of being wrong, reversibility, blast radius and novelty:

| Decision | Effort | Proceed once you have |
| --- | --- | --- |
| Small, familiar, easy to reverse | One or two sources | A credible precedent that fits |
| Material trade-off, moderate rework | A few targeted searches; three to five references | Comparable solutions, their observed outcomes, a credible alternative, failure modes |
| Hard to reverse, unfamiliar, disputed, or meant to differentiate | Several passes over independent primary sources | Current authoritative guidance, comparable outcomes, contrary evidence, validated key assumptions |

Start at level 1, and expect most of the effort to land there. Widen to levels 2 and 3 when:

- the shape names a defined, well-studied problem, as with alarm fatigue
- level 1 sources are thin, contradict each other, or all ship the same mediocre answer
- level 1 shows what people do but not why it works or when it fails
- the goal is to stand out, or to break a trade-off others accept.

Stay at level 1 when users rely on conventions, or when the governing docs and a comparable local precedent settle the choice, even if it is consequential. Stop when a small experiment would teach more than further reading, or more searching won't change the decision. If results repeat, refine the question rather than collecting more of the same.

## Find the strongest sources

Look first where people are under the most pressure to get the problem right: the highest **stakes**, the most **reps**, and the clearest **feedback** on results. Pressure makes tested practice likely there, not proven.

Before reading deeply, shortlist specific references for each level you search (named products, teams, people or disciplines) and rank them by those signs and by how closely their situation fits the user's. Check local references first when it is cheap: project patterns, earlier decisions, and docs for tools already in use. Keep private details out of public queries.

At level 3, go deep on one or two domains, and extract the mechanism that makes their solution work rather than its surface features. A broad hunt for novel ideas is the `creative-problem-solve` skill.

## Weigh the evidence

- Judge every reference by its outcome. Ask what outcome was observed and by what measure, whether the examples are independent (many articles repeating one report are one line of evidence), and what made the practice viable in their setting. Keep measured results, practitioner reports and your own inference distinct.
- Neither what people do nor what they write proves a practice works. Persistence can reflect switching costs, convergence can trace back to one influential default, and write-ups are filtered by hindsight, survivorship, novelty and the author's incentives. Evidence against the source's interest, such as reversals, migrations away and failure write-ups, is harder to fake. Popularity and vendor claims demonstrate nothing.
- For a material decision, look for people who tried the leading approach and abandoned it, and find the strongest case against the option you favour before committing. Don't anchor on the first good result or on an approach the user only hinted at.
- Weigh specificity and recency over format. Docs, standards and research anchor established practice; practitioner blogs and threads often carry the frontier.
- Read the levels against each other. Independent levels agreeing is strong evidence. A mechanism borrowed from another level is a hypothesis for the user's setting: validate it against the user's own success measure, cheaply where possible.
- Don't copy a reference whose situation differs materially from the user's (scale, team, resources, risk, users). Name the mismatch and take the lesson, not the machinery that only works in their situation. Count delay and maintenance as costs.
- If you can't search, say so, separate what you know from what you verified, and make no unsupported consequential commitment.

## Decide and continue

Start from the strongest reference that fits and adapt it rather than designing from scratch. Choose the smallest approach that meets the outcome. When evidence conflicts, explain the disagreement that matters and choose for this context. When evidence is weak, narrow the next step to a reversible experiment instead of handing the call to the user.

Tell the user what you decided, sized to the decision: a line for a small choice, a short note for a consequential one. Cover the references and the level each came from, the chosen approach and where it departs from them, why it fits, the key trade-off or assumption, and links for consequential claims. Mid-task, put it in your progress update and keep working without waiting for a reply. When the work leaves a durable record, such as a PR description or design doc, record consequential decisions there too. Don't end with a menu of options or an offer to proceed when the task already authorises action.
