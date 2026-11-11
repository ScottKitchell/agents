# AGENTS.md, CLAUDE.md, and rules

Checked against harness docs in November 2026. Re-check the links at the end if this is more than a few months old.

These files load into every session, so every line is paid for on every task. Generated or bloated instruction files lower task success and raise cost; short, human-curated files help.

## Files

- `AGENTS.md` is canonical. Codex, Cursor, Claude Code (v2.1.277 and later), and most other agents read it. Don't add a project `CLAUDE.md` by default.
- Claude Code skips `AGENTS.md` whenever a `CLAUDE.md`, `.claude/CLAUDE.md`, or `CLAUDE.local.md` exists in the working directory or above it. If Claude needs extra lines, make `CLAUDE.md` import `@AGENTS.md` and add only those lines. An existing symlink or import is harmless and never loads twice.
- Claude Code doesn't read `AGENTS.override.md`, `AGENTS.local.md`, or anything under `.agents/`.
- Put rules for one area in a nested `AGENTS.md` in that directory. It loads only when the agent works there.
- Codex caps combined project instructions at 32 KiB by default and truncates silently beyond that.
- Global instructions live in `~/.codex/AGENTS.md` and `~/.claude/CLAUDE.md` (Claude Code has no global `AGENTS.md`). Cursor keeps user rules in its settings.
- Use Cursor rules (`.cursor/rules/*.mdc`) only for behaviour Cursor alone needs. Prefer a nested `AGENTS.md` or a skill with `paths` for anything shared.

## Include

- How to verify a change, when it isn't the obvious command.
- Non-obvious conventions, and decisions that depart from defaults.
- Constraints: files that are generated, areas to leave alone, operations that are expensive or need approval.
- Known traps.
- Pointers to deeper docs, each with one line on what it holds and when to read it.

## Leave out

- Project overviews, architecture summaries, and directory trees. The agent can read the code.
- Style rules a formatter or linter enforces. Point to the config, or run the tool in a hook.
- Generic best practice and anything the README already says.
- Procedures needed only for some tasks. Make them skills.
- Rules added after a single past mistake that no longer apply.

## Shape

- Keep the root file under about 150 lines, ideally under 100. Split by directory or into skills before it grows past that.
- Use short bullets under a few headings.
- Before adding a line, search for one that conflicts with or duplicates it.
- Never ship raw `/init` output. Treat it as a draft and delete everything the agent could discover itself.

## Check

- Root file is under about 150 lines, with no contradictions or duplicated rules.
- Every pointer says what the target holds and when to read it.
- Any project `CLAUDE.md` imports or symlinks `AGENTS.md`, never a divergent copy.

## Current docs

- [AGENTS.md](https://agents.md)
- [Claude Code memory and CLAUDE.md](https://code.claude.com/docs/en/memory)
- [Codex AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md)
- [Cursor rules](https://cursor.com/docs/rules)
