# Agents

Skills and instructions I use to work with AI agents in a way that makes me more skilled over time, not less.

By default, AI produces slop. If you're not careful, it turns your thinking to slop too. This repo is my attempt to prevent that for myself and anyone else who finds it useful. Each resource pushes the agent to think clearly, explain its reasoning, and leave you understanding more than when you started.

Everything here is agent-agnostic. It should work in Claude Code, Codex, Cursor, Gemini, or any harness that reads `SKILL.md` and `AGENTS.md`.

## Skills

| Skill | What it does |
| --- | --- |
| [agent-docs](skills/agent-docs/SKILL.md) | Writes and maintains skills, `AGENTS.md`, subagents, commands, and plugins so they stay lean, focused, and work across Claude Code, Codex, and Cursor. |
| [concept-driven-design](skills/concept-driven-design/SKILL.md) | Keeps planning, code, architecture, and product UI organised around a small set of named concepts, so product, code, tests, and vocabulary tell one story. |
| [create-demo](skills/create-demo/SKILL.md) | Plans and creates internal demos: a focused story and the slides, docs, or posts to present it. |
| [creative-problem-solve](skills/creative-problem-solve/SKILL.md) | Finds fresh, non-obvious solutions when you're stuck or the obvious ones keep failing. |
| [expert-opinion](skills/expert-opinion/SKILL.md) | When the right approach is unclear, finds how experienced practitioners (in your field or others) already solve it, then decides and keeps going instead of handing the call back to you. |
| [human-writing](skills/human-writing/SKILL.md) | Makes human-facing writing clear, concise, and natural, and strips out AI tells. |
| [rapid-fire](skills/rapid-fire/SKILL.md) | Turns feedback, reviews, or notes into a short queue of decisions that need your judgement, each with a recommendation. |
| [strategy](skills/strategy/SKILL.md) | Develops, pressure-tests, or refines a company, team, or individual strategy for reaching an outcome under constraints and uncertainty. |
| [teach-me](skills/teach-me/SKILL.md) | Teaches a topic through small, concrete units built for fast understanding. Only runs when you ask for it. |
| [what-would-scott-do](skills/what-would-scott-do/SKILL.md) | Pressure-tests a plan, design, PR, or message with the questions I habitually ask (user goals, simplify, focus, concepts, automation, verification), checking what I've already said on the topic first. Only runs when you ask for it. |

Each skill's `README.md` explains why it exists, the research behind it, and how to test changes. Agents never load it.

`teach-me` and `what-would-scott-do` are manual-only. Their descriptions say so for any agent, but a description is only a hint, so each also carries thin adapters that switch off automatic selection: `disable-model-invocation: true` in the `SKILL.md` frontmatter (Claude Code and Cursor) and `agents/openai.yaml` with `allow_implicit_invocation: false` (Codex).

## Other resources

- [AGENTS.global.md](AGENTS.global.md): my global agent instructions, covering guiding principles, shared language, pushback, and writing style.
- [concept-driven-design/](concept-driven-design/): the longer write-up of Concept-Driven Design, plus draft blog posts about it.
- [subagents/search-engine/](subagents/search-engine/): a search subagent with setup for Cursor, Claude Code, and Codex.
- [AGENTS.md](AGENTS.md): rules for agents working in this repo. `CLAUDE.md` is a symlink to it.

## Installing

Install the skills globally with the [`skills` CLI](https://github.com/vercel-labs/skills) (Node.js 22.20 or later). It asks which skills and agents you want:

```bash
npx skills add ScottKitchell/agents -g
```

Add `--skill <skill-name>` to install a single skill, and run `npx skills update` to pull in later changes.

To use the global instructions, symlink `~/.codex/AGENTS.md`, `~/.claude/CLAUDE.md`, and `~/.gemini/GEMINI.md` to `AGENTS.global.md`. Cursor keeps global rules in its settings, so copy them there by hand.
