---
name: agent-docs
description: Write and maintain documents that coding agents read, including skills, AGENTS.md and CLAUDE.md, rules, subagents, commands, and plugins. Use when creating, editing, reviewing, or trimming any of them.
metadata:
  author: ScottKitchell
---

# Agent Docs

Every line of an agent doc costs context each time it loads and competes for the agent's attention. Write only what changes what the agent does.

## Choose the doc type

| What the agent needs | Write | Read first |
| --- | --- | --- |
| Facts every session in a repo needs | `AGENTS.md` | [instructions.md](references/instructions.md) |
| Rules for one directory or file type | Nested `AGENTS.md`, or a skill scoped with `paths` | [instructions.md](references/instructions.md) |
| A procedure or knowledge needed for some tasks only | Skill | [skills.md](references/skills.md) |
| A workflow the user triggers by name (a command) | Manual-only skill | [skills.md](references/skills.md) |
| Work done in its own context window, returning a result | Subagent | [subagents.md](references/subagents.md) |
| Distribution of skills, subagents, hooks, or MCP servers as one install | Plugin | [plugins.md](references/plugins.md) |
| A rule that must always hold | A test, linter, hook, or permission, not prose | |

Read the matching reference before writing. Harness formats change every few months: when a reference disagrees with the harness's current docs, follow the docs and update the reference.

## Write

- Start from the agent's job: what it will be doing when it reads this, and what it gets wrong without it. If you can't name a failure a line prevents, leave the line out.
- Include only what the agent can't infer from the code, the task, or its training: non-obvious conventions, constraints, traps, and how to verify the work.
- Leave out generic best practice, explanations of well-known concepts, summaries of code the agent can read, rules a linter enforces, background and rationale that don't change actions, and commentary about the doc itself (how it works, why it exists, its history).
- Write imperative instructions. Say what to do; reserve "don't" for real traps. Long lists of prohibitions make agents timid.
- Use precise terms the model already knows instead of defining them.
- State what done looks like and how to check it, and require evidence before claiming success.
- Say when to stop and ask the user, and what to ask. Otherwise agents guess.
- Put each gotcha at the step where it applies, not in a closing list.
- Keep one source of truth. Point to a file instead of copying it, and don't repeat a rule another loaded doc already states.
- Every pointer to another file says what it holds and when to read it.
- Keep content agent-agnostic. Describe actions ("ask the user", "search the codebase"), not one harness's tool names, paths, or syntax. Put unavoidable harness specifics in thin adapter files.

## Cut

Your drafts will be bloated, like every agent's. Apply the no-op test to every line: if deleting it wouldn't change what the agent does, delete it. Delete whole sentences rather than trimming words. A doc that improves usually gets shorter.

Check the doc against everything else that loads with it: global instructions, `AGENTS.md`, and installed skills. Remove contradictions and overlaps. Overlapping skills trigger unpredictably.

## Update an existing doc

Read the whole doc and anything that points to it first. Keep what works, fix the specific failure, and look for a line to delete for each line you add. When a model or harness changes, expect deletions rather than additions. Don't patch in a one-off rule for a single past mistake; fix the general instruction or leave it out.

## Verify

1. Run the format checks in the reference for the doc type.
2. Read the doc as its reader would: a fresh agent with no conversation context, seeing only the description or pointer first. Confirm it would know when to load the doc and what to do next.
3. For docs that matter, run a real task in a fresh session with and without the doc, and run prompts that should and shouldn't trigger it. Keep the doc only where it changes the outcome.
