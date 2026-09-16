## search-engine subagent

When you need context and do not yet know which sources hold it, delegate to the **search-engine** subagent instead of searching Slack, Notion, Linear, GitHub, Amplitude, the web, or other connected tools yourself. Use it to find the sources and excerpts first. If the source is already known and the lookup is one cheap call, do it yourself. For codebase structure, use the harness's code-exploration tools or agent.

Use a cheap, mid-level model for the `search-engine` subagent, for example (using the latest available model in the named family):
- **Cursor:** Composer
- **Claude:** Sonnet
- **Codex:** Terra
