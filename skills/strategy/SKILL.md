---
name: strategy
description: Develop, pressure-test, or refine a company, team, or individual strategy for reaching an outcome under constraints and uncertainty. Use for roadmaps, go-to-market, prioritisation, "how do we win", OKRs, career or personal direction, and reviewing an existing strategy. Not for scheduling tasks or executing an already chosen plan.
metadata:
  author: ScottKitchell
---

# Strategy

Develop the strategy with the user, usually over multiple turns. Work backwards from the desired outcome to discover what must become true, forwards to test whether it can, then choose where to concentrate effort. Refine at finer levels only where it improves decisions or enables delegation.

For a model of the finished reasoning (a team strategy with a written hand-off, and a short personal strategy), read [worked examples](references/examples.md).

## Concepts

- **State:** A situation described by conditions that can be checked. Current, desired, intermediate, and adverse states all use this meaning. Include only details that change a decision. If a goal can't yet be checked, making it checkable is part of the work.
- **Action:** An intervention intended to move between states, with the reason it should cause the change. Performing it does not guarantee the destination.
- **Pathway:** A possible sequence or combination of states and actions. It can branch, converge, run in parallel, or revisit a situation with different resources or knowledge.
- **Diagnosis:** An explanation of what prevents progress and where the most useful leverage lies. It separates causes from symptoms and states its uncertainty.
- **Guiding policy:** The principle that concentrates effort against the diagnosed challenge. It says what gets resources and what does not.
- **Signal:** An observable condition that tells us a pathway is working, failing, or no longer fits, paired with a **response**: continue, adapt, switch pathway, stop, or revisit the diagnosis or destination.
- **Hand-off:** A self-contained section of the strategy ready for a team, person, or agent to own.
- **Strategy:** A diagnosis, a guiding policy, a chosen pathway, and signal-response pairs, with the reasons it should work.

Keep evidence and assumptions visible. New knowledge from an experiment can itself be a useful state condition.

## Set the depth

Infer scope, decision, horizon, constraints, and desired effort from the request and context. Start with enough understanding to make useful progress; gather further input as the strategy develops. If the user is exploring, state provisional assumptions and proceed where their answer is not required.

Scale effort to consequences, uncertainty, reversibility, and appetite:

- **Quick exploration:** A short conversation or brief: provisional destination and diagnosis, a few materially different pathways, the critical assumption, and the next move.
- **Working strategy:** Verify the facts that drive the choice, compare credible alternatives, stress-test the preferred pathway, and detail near-term actions and hand-offs.
- **Consequential commitment:** Also investigate assumptions that could reverse the decision, resource conflicts, external responses, irreversible steps, and fallback feasibility. Make unresolved dependencies explicit before calling the strategy ready to commit.

These are effort guides. Every depth keeps the same reasoning, compressed for small requests. Respect a stated timebox and say what remains provisional.

## Collaborate across turns

Expect the destination, diagnosis, pathways, and choices to develop through conversation. Bring the user into the work when their context or judgement matters: clarifying success, correcting the diagnosis, surfacing missing alternatives, weighing trade-offs, and choosing commitments. Do not treat the initial request as the only opportunity for input or produce a finished strategy before resolving material user-dependent questions.

At a useful decision point, give a concise synthesis of what is known, the current recommendation and its reasoning, and the few questions or choices that need the user. Ask in small batches as they arise, rather than front-loading a questionnaire or requiring approval after every stage. Yield when an answer is needed; continue independent research where useful. Do not treat silence, provisional assumptions, or an agent recommendation as agreement. A small request or an explicit request for a single-pass draft can still be completed in one turn, with unresolved choices labelled.

Maintain a compact working summary across turns: current states and diagnosis, candidate and chosen pathways, supporting evidence and critical assumptions, settled decisions and their rationale, and open questions and next investigations. Update the affected parts when the user provides guidance, without restarting or reopening settled choices unless new evidence warrants it. Clearly distinguish exploration, a proposed strategy, and an agreed strategy.

## Research proactively

Actively build knowledge of the space throughout the process, rather than relying only on the user's account or waiting to be asked to research. Search relevant accessible internal documents and connected sources for context, capabilities, constraints, prior decisions, and earlier attempts. Search the web for external conditions, comparable approaches, stakeholder incentives, and evidence that could support or challenge the emerging diagnosis and pathways. Keep private information out of public queries. If a needed source is unavailable, state the gap and its effect on the strategy.

Investigate facts before asking the user to supply them when accessible sources can answer. Ask the user for private context, preferences, judgement, or authority that sources cannot establish. Follow promising leads and contrary evidence, scaling effort to the depth and decision value rather than searching everything. Use expert-opinion if available for unresolved professional trade-offs; the workflow works without it. Cite material evidence, separate observation from inference, and never invent numbers, certainty, stakeholder motives, or organisational commitments.

For a large space, prefer subagents, when available, for bounded searches or independent analyses that would otherwise crowd the main conversation. Suitable splits include internal context, external evidence, alternative pathways, stakeholder responses, and stress-testing. Delegate only useful independent work; a small strategy does not need a team of agents.

Give each subagent a clear question, relevant states and constraints, scope and effort limit, and a request for concise findings with source links, uncertainty, contrary evidence, and implications for the strategy. Keep bulk source material and exploratory detail in those investigations. The main agent synthesises findings, resolves contradictions and shared dependencies, and maintains the coherent strategy and conversation with the user. Parallel research does not delegate the user's decisions or authorise external commitments. If subagents are unavailable, use bounded sequential investigations and compact notes.

## 1. Define the desired state

Express the outcome as conditions that would be true, with success evidence and a horizon. Say whose outcome it is, why it matters, and which constraints must keep holding. Separate essentials from preferences, and state non-goals that prevent scope drift.

Challenge a destination that presupposes a solution. "A partner programme exists" may really mean "a repeatable source of profitable customers". For an ongoing objective, describe the condition to sustain and over what horizon.

Treat the destination as provisional. Test its feasibility against the current state and explain any revision rather than quietly lowering the bar.

## 2. Define the current state and diagnose

Gather the starting conditions that matter: assets and advantages, capabilities and weaknesses, commitments, resources, constraints, incentives, and external conditions. Skip exhaustive inventories and generic SWOT.

Write the diagnosis: what blocks progress, and which constraint or opportunity offers the most leverage. Label decision-critical claims as supported facts, assumptions, or unknowns, with sources or reasons, and note which would change the pathway if false. Don't wait for complete information.

**Checkpoint.** Before expanding pathways, state the desired state and diagnosis in a few lines and let the user correct them. Everything downstream depends on both. In a quick exploration, flag them as assumptions and continue.

## 3. Work backwards to discover pathways

Use **backcasting**: for each desired condition, ask what would need to be true immediately before it, and continue towards the current state, identifying the actions and causal mechanisms that could create each condition. An intermediate state must make the remaining challenge more tractable; the goal at a smaller number doesn't.

Explore materially different routes, including different ways to remove the central constraint or exploit an advantage. Stop when new branches no longer change the strategic choice, and don't present the option space as exhaustive.

Make dependency logic explicit:

- **AND:** Conditions that must all hold, possibly reached through parallel work.
- **OR:** Alternative conditions or routes that can each enable progress.

Don't force a sequence onto parallel work. Expose shared prerequisites, resource competition, and routes that close off other options. Backwards reasoning gives candidate logic to test, not proof of feasibility.

## 4. Work forwards and stress-test

Start from actual capabilities and resources. For each material transition, test the prerequisites, causal mechanism, effort, lead time, and dependencies. Ask what happens if the action fails, only partly works, is delayed, or succeeds in an unexpected way, including the cost of waiting.

Separate what we control (actions) from what we don't (outcomes and external events). Model adverse states or opportunities only when they change what we would do, and trace consequences through downstream dependencies.

When outcomes depend on other actors, apply **game theory** proportionately: their objectives, incentives, alternatives, information, and ability to act; their plausible responses to our move; our response to theirs. Look for cooperation as well as conflict, credible commitments, and differences in timing or bargaining power. Test several plausible behaviours rather than predicting one. Use formal payoffs only when evidence and decision value justify them.

For critical uncertainty, choose between researching, asking, running a bounded experiment, keeping an option open, or accepting the risk. Prefer evidence that discriminates between pathways, and consider whether learning will arrive before the decision becomes irreversible. An unsupported probability or weighted score adds no rigour.

## 5. Choose the strategy and make it usable

Choose the guiding policy and the pathway that fits it. Compare candidates on:

- leverage on the diagnosed constraint
- reversibility
- cost of delay
- learning value
- fit with capacity, taken together with the other actions

Explain why credible alternatives lose under the actual constraints, what trade-offs are accepted, and what will not receive effort. Keeping options open is not the same as committing to every option.

Check that actions reinforce one another and don't spend the same person's time or budget twice. A new capability can be part of the pathway, but don't assume it already exists.

Specify the first actions in enough detail to begin, the evidence that each state has been reached, and who owns the next decision where known. Owners, budgets, and dates are proposals until established, and a recommended strategy is not an approved commitment.

For each material contingency, pair a signal with a response. Give a threshold or review point where useful, who watches it, and enough lead time to act. Check that fallback resources will still exist when needed. A fallback that depends on the same failed assumption is not a fallback.

## Refine and hand off

Any chosen action can become a smaller strategy with the same five steps. Use **rolling-wave planning**: detail what is close enough to act on and leave distant or uncertain transitions coarse. Before refining a transition or writing a hand-off, read [refinement and hand-offs](references/refine-and-delegate.md).

## Present and maintain

Present the chosen approach and its reasoning first, then enough of the map, alternatives, assumptions, signals, and next actions to assess it. Scale the deliverable to the audience and decision: a personal strategy may be a few paragraphs, a company strategy a durable brief with a dependency map. See [output shape and maintenance](references/output-and-maintenance.md) for a default skeleton, the state/action table, diagrams, and how to update an existing strategy.

## Before finishing

- **Does it explain why the approach should work, and name the decisive uncertainties?** If not, it's a plan, not a strategy.
- **Does it make a real choice within resources?** Check for the bad-strategy marks: fluff in place of content, goals presented as strategy, a diagnosis that avoids the real challenge, and a list of objectives with no guiding policy.
- **Can someone act or take ownership tomorrow?** A neat graph and a long task list don't answer these questions.
