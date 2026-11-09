---
name: creative-problem-solve
description: Find fresh, non-obvious solutions to any kind of problem. Use when someone is stuck, obvious solutions keep failing, or they ask to brainstorm, "think outside the box", "think differently", or "get creative". Not for routine execution or questions with a known answer.
---

# Creative Problem Solve

Help the user escape the box they are thinking in. Most stuck problems are stuck because of the frame, not a lack of effort: everyone in the domain reaches for the same solutions. Other domains have often solved the same underlying structure in ways nobody here has considered.

The method: understand the problem more fully than it was stated, find many parallel universes where the same structure exists, raid each one for ideas, then judge hard and hand back only what is worth acting on.

## Concepts

- **Problem space:** The stated problem plus the underlying problems beneath it, who experiences each, and the constraints that genuinely hold.
- **The box:** The solutions anyone in the domain would reach for first. Writing them down makes them visible, so they can be avoided and used as the baseline for novelty.
- **Core structure:** The problem described in domain-free terms: the purpose to achieve, the forces and relationships involved, and the contradiction at its centre, stripped of jargon. "Patients drop out of a 6-week program" becomes "a commitment decays over time while its benefit is delayed and invisible".
- **Analogy universe:** Another domain where the core structure also exists. Each one is a source of knowledge, tested solutions, and failure stories.
- **Transferable mechanism:** The specific reason something works in an analogy universe, expressed so it can be carried back. "Casinos never show clocks" is an observation; "remove cues that prompt a stopping decision" is the mechanism.
- **Idea:** A transferable mechanism applied to the user's problem, with why it should work here and how to test it.

## Set the depth

Scale effort to the size and stakes of the problem, but lean broad. Breadth of analogies is where the value comes from, and a narrow search mostly rediscovers the obvious.

- **Small problem** (naming, a stuck bug, a single UX moment): a quick problem map, 10 to 15 analogies, a few explored properly, 3 to 5 ideas.
- **Medium problem** (a feature, a process, a team issue): a full problem map, 20 to 30 analogies, the most promising 6 to 10 researched, 5 to 8 ideas.
- **Large problem** (strategy, a market, an organisational or societal challenge): a deep problem map across stakeholders, 30+ analogies, broad research, and a ranked set of ideas grouped by underlying problem.

Respect a stated timebox. Ask the user a question only if the intended outcome is genuinely unclear and a wrong guess would waste the work; otherwise state the assumption and proceed.

## 1. Map the problem space

Restate the problem in one line, then dig beneath it with **5 Whys**. Don't stop at a single chain: branch wherever more than one answer is plausible, so you end up with a small tree of underlying problems rather than one root cause.

For each underlying problem, note:

- **Who** experiences it (users, buyers, operators, the team, the user themselves) and what progress they are trying to make.
- **What makes it hard**: the conflict or constraint at its centre. Many good problems are a contradiction ("we need it faster and more thorough").
- Which constraints are **real** and which are **assumed**. Assumed constraints are often the walls of the box.

Write down **the box**: the three to five obvious solutions, including any the user has already tried. Don't spend effort on them; they exist so later ideas can be checked against them.

Then write the **core structure** in domain-free language. This is the key that unlocks analogies, so make it abstract enough to travel. Separate the **purpose** (what must be achieved) from the **mechanism** (how it is currently attempted): the richest analogies share the purpose but use a different mechanism. Where there is a contradiction, name both sides, since other domains often resolve the same trade-off in ways that avoid it entirely. Write two or three versions at different levels of abstraction if the problem has several facets.

Check whether the stated problem is the right one to solve. If an underlying problem offers far more leverage, say so in the final response.

## 2. Generate analogy universes

List as many domains as you can where the core structure appears. Quantity first, judgement later.

Early ideas anchor later ones, for models as much as people. To counter fixation, generate category by category below, coming at each category fresh from the core structure rather than from the previous analogy. When an analogy feels like a variation of an earlier one, move to a different category.

Spread across **analogical distance**. Near domains (adjacent industries) are easy to transfer but rarely surprising. Very far domains break the frame but often don't survive the trip back. Research on design-by-analogy suggests the most useful ideas often come from the middle distance, so aim for a mix rather than maximum weirdness. Deliberately span:

- **Everyday life:** cooking, parenting, gardening, queues, dating, moving house, pets, sport.
- **Nature and science:** ecology, immune systems, evolution, ant colonies, physics, chemistry, geology, epidemiology.
- **Human systems:** militaries, religions, cities, markets, sports leagues, theatre, games, cults, prisons, hospitals, airlines, logistics, law.
- **History and craft:** guilds, explorers, monasteries, ancient engineering, oral traditions, navigation.
- **Technical and esoteric:** control theory, queueing theory, compilers, distributed systems, information theory, game theory, mechanism design, materials science, cryptography, typography.
- **Wild cards:** anything that sounds absurd at first. Jazz improvisation, beekeeping, heist films, sumo, Formula 1 pit crews, volcanoes. Absurd analogies are where the frame breaks; don't filter them yet.

Prefer analogies that share **relationships**, not surface features. A hospital waiting room is a weak analogy for a slow checkout page because both involve waiting; it is a strong one if, in both, uncertainty about wait time is the real pain.

Keep this list as working notes. It does not all go to the user.

## 3. Explore each universe

Go back to the user's original problem. For each promising analogy universe, ask:

- How does this domain handle the core structure? What do experts there know that we don't?
- What has been tried there and failed, and why?
- What would a practitioner from that domain do if handed our problem?
- What is the **transferable mechanism**, and does it survive the trip back?
- Where does the analogy **break**? The differences between domains show which parts of the mechanism need adapting, and sometimes the break itself is the insight.

Research where it adds substance: search the web for how the domain actually works, notable cases, and evidence, rather than relying on a vague impression of it. Check relevant internal or connected sources when the user's own context matters. Keep private information out of public queries. Never invent facts about a domain to make an analogy fit.

Explore broadly; it is fine for many universes to yield little. For a large problem, if subagents are available, split exploration across them by cluster of universes, each given the core structure, the underlying problems, and a request for transferable mechanisms with sources and why each should transfer. Synthesise their findings yourself.

Also look for **convergence**: when several unrelated domains independently arrived at the same mechanism, that mechanism is probably robust.

## 4. Judge and consolidate

Turn mechanisms into ideas for the user's problem, then judge them harshly. Weigh:

- **Fit:** does the mechanism's reason for working actually hold in the user's context?
- **Leverage:** how much of the underlying problem does it address, and for whom?
- **Novelty:** does it get the user somewhere outside the box? An idea that restates one of the obvious solutions in new words doesn't count.
- **Feasibility:** cost, time, risk, and reversibility given real constraints.
- **Testability:** can it be tried cheaply before committing?

Combine ideas that reinforce each other. Drop clever-but-useless analogies even if they were fun to find. Keep a wild idea when it reframes the problem usefully, even if it is not directly actionable, and label it as a reframe.

## 5. Respond

Choose the format that best serves the user and the problem; there is no fixed template. The response should generally:

- **Lead with the best ideas**, ranked, each with the source analogy, the transferable mechanism, how it applies here, why it should work, and a cheap first test.
- **Share the reframe** if the problem map revealed a better problem to solve or an assumed constraint worth challenging.
- **Show the analogy behind each idea** briefly and vividly. The analogy is what helps the user think differently next time, not just this time.
- Optionally list the other universes explored in a line or two, so the user can pull on a thread you didn't.

Keep the 5 Whys tree, the full analogy list, and dead ends out of the response unless they change the user's understanding or the user asks for them. Separate evidence from speculation, and say what remains untested.
