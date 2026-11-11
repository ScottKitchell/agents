# Commands and plugins

Checked against harness docs in November 2026. Plugin formats change fastest, so read the current docs before writing a manifest.

## Commands

Claude Code and Cursor have merged custom commands into skills, and Codex invokes skills by name with `$skill-name`. Write a new command as a manual-only skill (see [skills.md](skills.md)), and migrate old command files the same way.

## Plugins

A plugin packages skills, subagents, hooks, and MCP servers for installation through a marketplace. Write and test the components first; the plugin only wraps them. Use one only when you need marketplace distribution or must ship a skill together with its hooks or MCP server. A shared skills folder is enough otherwise.

Keep a single `skills/<name>/SKILL.md` tree at the plugin root and add one manifest per harness:

| Harness | Manifest | Marketplace |
| --- | --- | --- |
| Claude Code | `.claude-plugin/plugin.json` (the only file in that folder; components stay at the plugin root) | `.claude-plugin/marketplace.json` |
| Codex | `.codex-plugin/plugin.json`, with `"skills": "./skills/"` | See Codex docs |
| Cursor | `.cursor-plugin/plugin.json` | `.cursor-plugin/marketplace.json` |

## Check

- Each manifest's name matches across harnesses and is kebab-case.
- Every component the plugin ships still works when installed on its own.

## Current docs

- [Claude Code plugins](https://code.claude.com/docs/en/plugins/create) and [manifest reference](https://code.claude.com/docs/en/plugins/manifest-reference)
- [Codex plugins](https://developers.openai.com/plugins/build/plugins)
- [Cursor plugins](https://cursor.com/docs/plugins) and [reference](https://cursor.com/docs/reference/plugins)
