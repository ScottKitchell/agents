# Subagents

Checked against harness docs in November 2026. Re-check the links at the end if this is more than a few months old.

A subagent runs in its own context window and returns only its final message. Use one when the work generates a lot of intermediate context the parent doesn't need (searching, exploring, reviewing) or needs narrower tools or permissions. Otherwise a skill is simpler.

## Files

Write the Markdown file as the canonical source and add a TOML adapter for Codex.

| Harness | Project path | Personal path | Format |
| --- | --- | --- | --- |
| Claude Code | `.claude/agents/<name>.md` | `~/.claude/agents/` | Frontmatter `name`, `description`, optional `tools` and `model`; body is the system prompt |
| Cursor | `.cursor/agents/<name>.md` | `~/.cursor/agents/` | Frontmatter `name`, `description`, optional `model`, `readonly`, `is_background`; also reads `.claude/agents/` |
| Codex | `.codex/agents/<name>.toml` | `~/.codex/agents/` | Required `name`, `description`, `developer_instructions`; optional `model`, `model_reasoning_effort`, `sandbox_mode` |

Copy the Markdown body into `developer_instructions` and start the TOML with a comment naming the Markdown file as canonical, so the two stay in sync.

## Write

- The description is the delegation trigger: what the subagent handles, when to delegate to it, and what it is not for.
- The body is the whole briefing for an agent with no conversation history. State its role, the input it will receive, what to do, when to stop, and the exact shape of the result.
- Define the output contract precisely. The parent sees only the final message.
- Grant the least access that works. Make it read-only unless it must change things.

## Check

- Names match across the Markdown and TOML files, and the Codex instructions match the Markdown body.
- A fresh agent given only the description would know when to delegate, and given only the body would know what to return.

## Current docs

- [Claude Code subagents](https://code.claude.com/docs/en/sub-agents)
- [Codex subagents](https://learn.chatgpt.com/docs/agent-configuration/subagents)
- [Cursor subagents](https://cursor.com/docs/subagents)
