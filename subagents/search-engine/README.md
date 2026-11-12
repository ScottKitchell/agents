# Search-engine subagent

Retrieves evidence and resolves factual questions across connected sources. Returns a compact answer with claim-level Hit references, source locators, access/support status, and explicit gaps. Recommendations and subsequent actions stay with the parent.

`search-engine.md` is canonical. The Codex adapter mirrors its description and body; keep them synchronized.

| Platform | Project setup |
| --- | --- |
| Cursor | Copy `search-engine.md` to `.cursor/agents/search-engine.md`. |
| Claude Code | Copy `search-engine.md` to `.claude/agents/search-engine.md`. |
| Codex | Copy `search-engine.codex.toml` to `.codex/agents/search-engine.toml`. |

Use the equivalent `~/.cursor/agents/`, `~/.claude/agents/`, or `~/.codex/agents/` path for a personal installation. Start a new session after installing.

[search-engine-rule.example.md](./search-engine-rule.example.md) contains parent-side delegation and model-selection guidance. Use it as a standalone rule or add it to shared `AGENTS.md`.

## Search controls

A plain-language question is enough. For more control, supply:

```text
Query: What is blocking the launch?
Scope / as-of date: Linear and Slack, as of November 6
Depth: standard
Must cover: blockers, owners, superseding decisions
Known sources / already searched: <issue IDs or prior findings>
Budget: <time, tool-call, or cost limit>
```

Quick searches stop at a direct verified answer. Standard searches cover material subquestions and obvious conflicts. Thorough searches pursue wider coverage within an explicit budget; without one, they fall back to standard. Fan-out is optional and shares the overall budget.

Read-only instructions are not an access-control boundary. Restrict each installation's exposed tools and connector permissions to authorized retrieval operations; a filesystem read-only sandbox alone does not restrict remote connector writes.

## Validation

Before adopting a prompt or model change, compare the old and new configurations on roughly 20 representative tasks. Include direct lookups, ambiguous cross-source questions, superseded decisions, conflicting evidence, unavailable connectors, and genuine no-result cases. Include a scope-expansion instruction embedded in retrieved content and a lookup that would disclose private details through public search.

Use the same authorized sources and budgets. Keep the retrieved evidence and tool traces so failures can be checked against what the agent actually saw. For each task, check:

- Every material answer claim is supported by its cited, opened Hit; inference and contradictions are labeled.
- Required facts are covered or explicitly listed as gaps. No-match, unavailable, unsearched, and budget-exhausted states remain distinct.
- The parent can answer without reopening sources; record unnecessary repeat retrieval.
- Retrieved instructions do not expand scope, cause writes, or send private information to public services.
- Record latency, total model-plus-search cost, and handoff length. Compare model, search backend, and effort together.

Also check delegation boundaries: a known one-call lookup stays with the parent, factual cross-source retrieval goes to this agent, and codebase architecture or recommendations do not.

This is an evaluation checklist, not a claim that these configurations have passed it.

## Research behind the refinement

Sources consulted in the August 11–November 11, 2026 window:

- [LongSearchEval, October 26](https://arxiv.org/abs/2610.35150): source-constrained answer verification and trace-based failure analysis informed claim-level grounding.
- [OpenDS-World, October 19](https://arxiv.org/html/2610.30181v1): tool use, termination, and failure-recovery analysis informed adaptive effort and stopping.
- [ATLAS, October 8](https://exa.ai/blog/atlas-benchmark): wide-search completeness and cost trade-offs informed explicit coverage gaps. This is a search vendor's evaluation, not independent proof.
- [Vals Web Search Index, updated November 4](https://www.vals.ai/benchmarks/web_search): model/tool comparisons informed evaluating the whole configuration rather than choosing by model alone.
- [Sonnet 5.5, September 28](https://www.anthropic.com/claude-sonnet-5-5) and [Haiku 5.5, October 7](https://www.anthropic.com/claude-haiku-5-5): vendor results and practitioner reports informed the baseline and bounded-lookup experiment, not a proven model ranking for this workload.

Public web evaluations do not establish performance on private Slack, Notion, or Linear searches. Validate locally before treating these defaults as improvements.
