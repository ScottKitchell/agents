# Agent Instructions

## Purpose

- This repository contains reusable, agent-facing resources such as skills and instruction files.
- Keep every resource agent- and harness-agnostic by default.

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
