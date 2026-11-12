## search-engine subagent

When you need context and do not yet know which sources hold it, delegate to the **search-engine** subagent instead of searching Slack, Notion, Linear, GitHub, Amplitude, the web, or other connected tools yourself. Use it to find the sources and excerpts first. If the source is already known and the lookup is one cheap call, do it yourself. For codebase structure, use the harness's code-exploration tools or agent.

Send the factual question and, when useful, scope/as-of date, depth (`quick`, `standard`, or `thorough`), must-cover facts, known sources/already-searched findings, and a budget. Give thorough searches an explicit budget; otherwise the agent uses standard depth. Keep recommendations and next actions with the parent.

Configure the model in the parent or harness, not in source workers. Start with a fast mid-level model at medium effort (where supported); these are baselines to evaluate, not fixed requirements:

- **Cursor:** latest available Composer
- **Claude:** Sonnet 5.5; test Haiku 5.5 for bounded lookups and extraction
- **Codex:** latest available Terra

If material facts remain unresolved after a bounded attempt, the parent may retry the remaining question with a stronger configured model and the evidence already found. Workers must not independently upgrade models or multiply retries. Compare model, search tool, and effort together on representative tasks; do not assume the largest or newest model is the best value.
