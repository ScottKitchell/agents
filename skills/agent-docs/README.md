# agent-docs

One skill for writing and maintaining anything a coding agent reads: skills, `AGENTS.md`, rules, subagents, commands, and plugins. `SKILL.md` holds the rules shared by every doc type; `references/` holds the format details for each type and each harness (Claude Code, Codex, Cursor).

## Why it exists

Agent-written docs drift into commentary, repetition, and generic advice that cost context without changing behaviour. Skill descriptions summarise the process instead of saying when to use the skill, and frontmatter such as author and invocation mode gets left undecided. Harness-specific skill creators also produce docs that only work in one agent. This replaces Anthropic's `skill-creator` with a lean, agent-agnostic alternative.

Design choices, from research in November 2026:

- One entry point with a reference per doc type, following Matt Pocock's [writing-for-agents](https://www.aihero.dev/skills-writing-for-agents).
- Keep instruction files short and limited to what the agent can't infer. Generated or bloated `AGENTS.md` files lowered task success and raised cost in 2026 studies ([summary](https://codex.danielvaughan.com/2026/07/27/do-auto-generated-agents-md-files-actually-help-codex-cli/)).
- Require verification steps, ask-the-human points, and gotchas placed where they apply. Their absence was the most common skill smell in a [survey of 238 SKILL.md files](https://codex.danielvaughan.com/2026/07/13/configuration-smells-agents-md-skill-md-codex-cli-detection-remediation-lint-leakage-context-bloat/).
- Manual-only skills need three adapters, because Codex ignores `disable-model-invocation`.

## Iterating

- Harness formats change every few months. Each reference has a "Current docs" list; re-check those links and update the "Checked" date.
- Test a change by asking a fresh agent session to create or trim a skill and an `AGENTS.md`, with and without the skill, then compare the results.
- Apply the skill to itself: every change should leave it no longer than it needs to be.
