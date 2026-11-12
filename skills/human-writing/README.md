# human-writing

Makes prose for people purposeful, clear, and natural. Combines shared communication principles and removal of AI tells with references for distinct reader tasks.

## Why it exists

Agent prose is padded and formulaic: throat-clearing, recaps, manufactured contrasts, rhetorical questions, bullet lists for symmetry, and hedging that hides the actual view. Readers notice and stop trusting it. This skill applies to any human-facing deliverable (messages, docs, tickets, PRs, copy), not to code or analysis without a written output.

Its "remove" list overlaps the style section of my global instructions (`AGENTS.global.md`). That's deliberate: the skill has to work for people who don't use those instructions.

## Structure

The core owns audience, purpose, voice, and prose quality. References cover messages, documents, overviews, review comments, and product copy. They load by reader task rather than channel: a decision request in Slack and email shares guidance, while a reference document and an essay need different structures.

Specialist skills retain ownership of workflows, required content, and formats. This skill works without them and adds writing judgement when they are available.

The approach draws on [Mailchimp's shared principles and content-specific guidance](https://styleguide.mailchimp.com/), [Diátaxis's distinction between documentation needs](https://diataxis.fr/), and [Google's guidance on actionable review comments](https://google.github.io/eng-practices/review/reviewer/comments.html). These are design precedents, not evidence that this skill improves agent output.

## Iterating

- Compare real drafts with and without the skill. Check whether the intended reader can understand, decide, or act with less effort while the author's meaning and uncertainty survive. Shorter is useful only when nothing necessary is lost.
- Cover an async request, a standalone guide, a change overview, a review comment, and an interface error. Also check an essay opening and a sensitive message so directness does not become a rigid template.
- Check that only relevant references load and that specialist formats remain intact. Try code-only work, analysis without a writing deliverable, and verbatim transcription as near misses for activation.
- Check the agent returns the finished copy without explaining its edits.
- Add a tell to the "remove" list only when it recurs across drafts, not for a one-off.
