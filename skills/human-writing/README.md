# human-writing

Makes prose for people clear, succinct, and natural: lead with the point, cut what doesn't serve the purpose, and remove the tells of AI-generated writing.

## Why it exists

Agent prose is padded and formulaic: throat-clearing, recaps, manufactured contrasts, rhetorical questions, bullet lists for symmetry, and hedging that hides the actual view. Readers notice and stop trusting it. This skill applies to any human-facing deliverable (messages, docs, tickets, PRs, copy), not to code or analysis without a written output.

Its "remove" list overlaps the style section of my global instructions (`AGENTS.global.md`). That's deliberate: the skill has to work for people who don't use those instructions.

## Iterating

- Test by revising a real, bloated draft. A good result is shorter, keeps the author's meaning and uncertainty, and doesn't become denser just to cut words.
- Check the agent returns the finished copy without explaining its edits.
- Add a tell to the "remove" list only when it recurs across drafts, not for a one-off.
