# Output shape and maintenance

## Default skeleton

Use this for a quick exploration, and as a starting point for larger work. Cut sections that don't help the decision and expand those that do. Put the chosen approach and its reasoning first. During development, present only the parts useful for the next conversation, label provisional choices, and include the open questions needing user input. The skeleton does not require a complete strategy in the first turn.

1. **Destination:** the desired state, success evidence, horizon, and non-goals.
2. **Diagnosis:** the current state in a few lines, the binding constraint, and key assumptions labelled as fact, assumption, or unknown.
3. **Options:** a few materially different pathways, each with its mechanism and main risk.
4. **Choice:** the guiding policy, the chosen pathway, why alternatives lose, and what will not receive effort.
5. **Signals and responses:** observable conditions paired with what we would do.
6. **Next move:** the first actions, who decides, and any hand-off ready to give.

A personal strategy may fit in a few paragraphs. A company strategy may need a durable brief with supporting evidence and a dependency map.

## Representing pathways

Default to readable prose and a compact table. Use stable state labels (S0, S1a, S1b) when states are cross-referenced.

| From | Action and why it should work | To and attainment evidence | Dependencies and uncertainty |
| --- | --- | --- | --- |

Add a Mermaid diagram when branching, convergence, or dependencies are easier to see than to read. Use a formal graph or machine-readable representation only when repeated updates, analysis, or tooling need one. If you keep several views, treat one as authoritative and derive the others from it.

## Updating an existing strategy

1. Compare new evidence with the assumed state and diagnosis.
2. Identify what changes the choice, and what doesn't.
3. Revise affected pathways, signals, and hand-offs, and leave the rest alone.
4. Record why important choices were made and what would reopen them.

Review on meaningful signals and a sensible cadence. Don't wait for a calendar date once a critical assumption has failed.
