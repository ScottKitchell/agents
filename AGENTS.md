# Agent Instructions

## Purpose

- This repository contains reusable, agent-facing resources such as skills and instruction files.
- Keep every resource agent- and harness-agnostic by default.
- Update `README.md` in the same change whenever you add, remove, rename, or change the purpose of a resource, so it never goes stale.

## Portability

- Prefer open or shared standards that work across agents.
- Use standard formats such as `SKILL.md` when they can express the requirement.
- Use `.agents/` for shared agent configuration instead of a vendor-specific directory such as `.codex/`, `.claude/`, or `.cursor/`.
- Keep shared instructions in `AGENTS.md`; symlink `CLAUDE.md` to it instead of maintaining a divergent copy.
- Do not add vendor-specific metadata, invocation rules, tools, or directory layouts when portable instructions are sufficient.

## Agent-Specific Configuration

- Add agent-specific configuration only when a necessary behavior cannot be expressed portably.
- Keep the portable resource canonical and make platform-specific files thin adapters.
- When agent-specific configuration is necessary, support Codex, Cursor, and Claude at minimum.
- Document the equivalent behavior for each supported agent and why the adapters are needed.

## Creating and Installing Skills

- Create new skills in this repository under `skills/<skill-name>/`, with `SKILL.md` as the portable entrypoint. Keep the repository copy canonical.
- Install skills globally with the `skills` CLI: `npx skills add ScottKitchell/agents -g --skill <skill-name>`. Let the CLI place skills in each agent's directory instead of linking them by hand.
- The CLI installs from GitHub, so push skill changes first, then run `npx skills update` to apply them.
- When moving an existing skill here, preserve its content and remove the superseded vendor-specific installation after verifying the shared installation. Resolve any differing existing copies before replacing them.

## Global Instructions

- `AGENTS.global.md` is the canonical copy of the user's global agent instructions.
- Install it by symlinking each agent's global instructions file to it: `~/.codex/AGENTS.md`, `~/.claude/CLAUDE.md`, and `~/.gemini/GEMINI.md`. Cursor keeps global rules in its settings, so copy changes there by hand.
