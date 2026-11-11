# what-would-scott-do

Pressure-tests a plan, design, PR, ticket, or message with the questions I habitually ask (user outcome, simplify, focus, concepts, automation, verification, decisions), after checking what I've already said on the topic. It runs only when explicitly invoked.

## Why it exists

People ask "what would Scott think of this?" before or instead of asking me. This skill answers from my recorded decisions and recurring questions, so they get the pushback without waiting for a review, and I see fewer avoidable issues.

Design choices:

- **Evidence first.** It searches what I've written (Slack, Linear, Notion, PRs, code, transcripts) before applying generic questions, and weights my own words above agent-drafted comments posted under my name.
- **Lenses, not a checklist.** Questions that find nothing are left out of the report.
- **Manual-only**, because it imposes one person's opinions. It carries the three manual-only adapters described in the `agent-docs` skill.

## Iterating

- Update the questions when I notice myself asking a new one repeatedly in reviews, or stop asking an old one.
- Test on a real PR or plan that I've already reviewed, and compare the report with my actual comments.
