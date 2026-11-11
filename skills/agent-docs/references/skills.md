# Skills

Checked against harness docs in November 2026. Re-check the links at the end if this is more than a few months old.

Claude Code, Codex, and Cursor all read the open [Agent Skills format](https://agentskills.io/specification). Write to it.

## Layout

```
skill-name/
├── SKILL.md            # Required
├── references/         # Docs loaded only when SKILL.md points to them
├── scripts/            # Code for deterministic or fragile steps
├── assets/             # Templates and data the output uses
├── agents/openai.yaml  # Codex adapter, only when needed
└── README.md           # For maintainers; never loaded by the agent
```

- Keep `SKILL.md` well under 500 lines. Most good skills are under 100.
- Move content that only one branch of the task needs into `references/`, one level deep, with a pointer that says when to read it.
- Add a script only when the step must be exact or repeatable. Reference it by path relative to the skill root.
- Put everything about the skill, as opposed to instructions for the agent, in `README.md`: what the skill is, the problem it solves, and how to iterate on it (scripts, evals, how to test a change). Keep it short. `SKILL.md` never points to it, and nothing the agent needs lives only there. Use no other meta files (no `SPEC.md`, changelog, or sources file); fold them into the README.
- Install locations differ by harness (Codex and Cursor read `.agents/skills/`; Claude Code reads `.claude/skills/`). Follow the host repo's install convention rather than copying folders by hand.

## Frontmatter

Always set these:

```yaml
---
name: skill-name
description: What it is. Use when ...
metadata:
  author: owner-name
---
```

- `name`: lowercase letters, digits, and single hyphens, at most 64 characters, matching the folder name.
- `metadata.author`: the person or organisation that owns the skill. Use the repository owner or git user name; ask once if neither is clear. Keep it under `metadata`, because some uploaders reject unknown top-level keys.
- Invocation: decide it explicitly for every skill (see below).

Add other fields only when they change behaviour:

- `paths`: glob patterns that limit automatic activation to matching files (Claude Code, Cursor).
- `compatibility`: real environment requirements such as required CLIs or network access.
- `allowed-tools`: experimental and inconsistently supported. Use it only to pre-approve narrow commands.
- Harness-only fields such as Claude Code's `context: fork`, `model`, or `argument-hint` are ignored elsewhere. Use one only when the behaviour can't be portable, and make sure the skill still works without it.

## Invocation

Decide whether the agent may load the skill on its own or only the user may invoke it. If the right choice isn't clear from the request, ask.

Make it manual-only when the skill has side effects, is expensive, imposes a persona or opinionated workflow the user wants to control, or would misfire on loosely related tasks. Leave it automatic when it is guidance the agent should apply whenever the situation arises.

A manual-only skill needs all three of these, because each harness honours a different one:

1. `disable-model-invocation: true` in the frontmatter (Claude Code, Cursor).
2. `agents/openai.yaml` (Codex ignores the frontmatter flag):

   ```yaml
   policy:
     allow_implicit_invocation: false
   ```

3. A description that ends with "Use only when the user explicitly invokes this skill." (for harnesses that support neither).

Uploads to claude.ai and the Claude Skills API reject `disable-model-invocation`. Remove it from copies sent there.

## Description

The description is the trigger. Harnesses load every skill's description into every session, decide from it alone whether to load the skill, and shorten or drop descriptions when they exceed their budget. It says what the skill is and when to use it, nothing else.

- Lead with what the skill is or does, in plain words, then "Use when …" with the situations and words a user would actually use.
- Add "Not for …" only to separate it from a neighbouring skill that would otherwise compete.
- Leave out the process, steps, principles, and output format. The body holds those.
- Keep it to one to three sentences, ideally under 300 characters.

Weak: `Uses a three-pass method to analyse PR feedback, cluster themes, then rank them by impact.`
Strong: `Turns PR review comments into a ranked list of changes to make. Use when asked to triage, summarise, or act on review feedback.`

## Body

The body loads only after the skill triggers, so it starts with the work.

- Skip introductions, "Overview", "When to use this skill", and any statement about what the skill is. The description already did that.
- Give imperative steps with explicit inputs and outputs. Include a plan step for complex work, a verification step, and the point where the agent should ask the user.
- Write instructions meant to persist across later turns as standing rules, since the body isn't re-read each turn.
- Write for the class of task, not the run that inspired the skill: strip one-off file names, repos, and examples that won't generalise.

## Check

- Frontmatter parses, and `name` matches the folder.
- `metadata.author` is set, and the invocation decision is reflected in all three manual-only adapters (or none).
- If `skills-ref` is installed, `skills-ref validate <skill-dir>` passes.
- For automatic skills, check the description triggers on three realistic prompts and stays quiet on three near misses.

## Current docs

- [Agent Skills specification](https://agentskills.io/specification)
- [Claude Code skills](https://code.claude.com/docs/en/skills)
- [Codex skills](https://learn.chatgpt.com/docs/build-skills)
- [Cursor skills](https://cursor.com/docs/skills)
