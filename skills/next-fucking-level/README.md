# next-fucking-level

A heavyweight, collaborative process for writing or speech that has to move a reader: they feel seen, understood, and cared for, and they experience the message instead of being told it. It researches the reader and subject in depth, agrees a brief and creative direction with the user, then drafts and edits against those decisions. The user controls meaning, voice, direction, and when the piece is final; the agent handles routine editorial work.

It is manual-only. It commits to deep research and creative exploration, so it should never fire on an ordinary message. The adapters are `disable-model-invocation: true` in the frontmatter (Claude Code, Cursor) and `agents/openai.yaml` (Codex).

## Why it exists

Agents default to telling. They state the conclusion ("Now is the time to act"), summarise the feeling, and close with a call to action. They also write from their first idea and shallow context, which produces what anyone would have written. This skill forces depth before drafting and real editing after it, with the user as co-author and final judge.

It sits beside `human-writing`, which makes routine communication clear and efficient. Its voice rules still apply here.

## Research behind it

**Discovery.**

- **Laddering.** The "five whys" on the reader comes from [means-end laddering](https://en.wikipedia.org/wiki/Ladder_interview) (Reynolds and Gutman), which climbs from attributes to consequences to personal values. UX researchers warn that bare, repeated "why" questions [feel interrogative and lead the witness](https://nngroup.com/articles/leading-questions/), hence the curious-question rule, and that [five is a guide, not a rule](https://dovetail.com/design-thinking/five-whys/).
- **Voice-of-customer research.** Copywriters [mine reviews](https://copyhackers.com/how-to-do-rapid-fire-review-mining/), [Reddit, and forums](https://wynter.com/post/collecting-voice-of-customer-data) for readers' exact words.
- **The brief.** Agency account planners write a [single-minded proposition](https://queerideas.co.uk/?p=238) built on a human insight, and compress a brief to [Get / Who / To / By](https://medium.com/@baiba.matisone/origin-of-the-get-who-to-by-model-0ed51eafd65d). The brief is the user's sign-off point before drafting and the record of decisions throughout revision.

**Getting past the obvious.** Upworthy [wrote 25 headlines per post](https://www.niemanlab.org/?p=71524), a habit borrowed from The Onion. Tim Hurson's [three-thirds model](https://coschedule.com/blog/headline-writing-exercises) holds that the first third of ideas are the obvious ones.

**Craft.**

- **Arc between what is and what could be, with the audience as hero.** [Nancy Duarte](https://www.duarte.com/resources/secret-structure-great-talks/).
- **"But" and "therefore", not "and then".** Trey Parker and Matt Stone's [beat test](https://nofilmschool.com/2015/04/tony-zhou-storytelling-video-essay-f-fake-therefore-but-and-then).
- **Anecdote, bait, and reflection.** Ira Glass's [building blocks](https://www.storycenter.org/storycenter-blog/blog/2013/7/1/ira-glass-on-storytelling).
- **Every sentence pulls into the next.** Joseph Sugarman's ["slippery slide"](https://larslofgren.com/joseph-sugarman/).
- **Feeling seen.** Motivational interviewing's [complex reflections](https://pmc.ncbi.nlm.nih.gov/articles/PMC6039097) predict change better than simple ones, and [matching the person's language](https://pmc.ncbi.nlm.nih.gov/articles/PMC5018199) predicts perceived empathy.
- **Stories lower resistance.** [Narrative transportation](https://en.wikipedia.org/wiki/Transportation_theory_(psychology)) reduces counter-arguing. Corny or inauthentic stories [trigger their own resistance](https://www.mcm.uni-wuerzburg.de/fileadmin/06110000/2026/AppelAffectiveResistance.pdf), hence "keep it true".
- **One person over statistics.** The [identifiable victim effect](https://www.gsb.stanford.edu/insights/increase-charitable-donations-appeal-heart-not-head). A [preregistered replication](https://stafforini.com/works/small-2007-sympathy-callousness-impact/) failed, so treat it as practitioner wisdom.
- **Commands backfire.** [Psychological reactance](https://www.psypost.org/forceful-language-makes-people-resist-health-advice/) research in health messaging.

**Editing.** George Saunders [rereads the whole piece as a first-time reader](https://advicetowriters.com/advice/wheres-the-needle) each pass. Robert Gottlieb describes editing as [candid service to the author](https://www.npr.org/2023/01/03/1146641641/robert-gottlieb-caro-power-broker-turn-every-page-lizzie-gottlieb): both sides opinionated, the author's book. Hence the user's final say on meaning, voice, and direction, with routine edits handled by the agent.

These are design precedents, not evidence that the skill improves agent output. Storytelling frameworks are optional techniques chosen for the brief. Research ends when there is enough evidence to support the insight and distinguish creative directions; inferred motives remain hypotheses.

## Iterating

Compare the previous and revised skill on the same briefs in fresh sessions. Include a short piece, a speech, and an existing draft needing revision. Judge quality alongside user effort: useful questions and decisions, repeated approvals, and unnecessary restarts.

- Check that research distinguishes sourced observations, user context, and hypotheses; quotes and factual claims remain traceable. Thin evidence should lead to an explicit gap, not invented emotional depth or a generalisation from one anecdote.
- Check that the agent gets agreement on the brief and a genuinely distinct creative direction, recommends choices, and handles routine edits itself. Ten cosmetic variations do not count as creative breadth.
- Try a factual or action-oriented piece. Necessary information, numbers, and explicit next steps should survive without a forced story or emotional arc.
- Give feedback that changes one line, then feedback that changes the audience. Only the latter should reopen the reader brief. Check that settled decisions persist across turns.
- Check that the agent delivers when no material issue remains and waits for feedback, rather than polishing indefinitely or asking the user to declare completion. Placeholders and material uncertainty must remain visible.
- Confirm it never loads unless invoked: a compelling launch email request should not trigger it in Claude Code, Cursor, or Codex.
