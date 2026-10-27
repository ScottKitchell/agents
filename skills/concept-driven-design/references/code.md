# CDD for Code

Code expresses the model through names, types, and outline. A reader should find the primary concept quickly and predict its behaviour without reconstructing meaning from scattered details.

## Names

- Name what something means, not the mechanism. `Helper`, `Manager`, `Utils`, `data`, `info`, `handle`, and `process` are warning signs.
- Use one name per idea across types, functions, files, tests, logs, and analytics. Reuse the name the model already has before inventing a synonym.
- When a concept is redefined or renamed, change it everywhere: types, files, tests, fixtures, and corresponding UI copy.

## Outline

- **File or type**: put the primary concept first (main type, class, or exported function), supporting parts below. Order members by the concept's story, such as its lifecycle, rather than alphabetically or by access modifier.
- **Function**: group related statements and separate meaningful steps with blank lines so the body reads as the concept's story. Extract a step when it has a meaningful name, not merely to shorten the function.
- **Module**: keep a concept's parts together. A concept may span several files, and several small related concepts may share one.

Follow the repo's conventions where they conflict. CDD does not prescribe a style, paradigm, or one-concept-per-file rule.

## Types

- Encode concepts in types. Prefer discriminated unions or separate types over flag combinations that allow invalid states.
- A boolean parameter or optional field that changes behaviour often hides a second concept.
- Do not let a type keep last year's meaning. If its fields or invariants changed, revisit its name and boundary.

## Changes

- When a change needs a special-case `if`, ask whether the concept is wrong before adding it. Prefer redesigning or splitting a weak concept over accumulating exceptions.
- Keep refactors proportional. Fix drift in what you touch; note larger drift rather than expanding scope without agreement.
- Add no abstractions for concepts that do not exist yet.

## Tests

- Name tests after concept behaviour: "subscription stays active during the payment retry period".
- Group tests by concept so the suite's outline matches the model.

## Review

Flag:

- Drift between a name and what the code now does
- Synonyms for one idea, or one name used for several
- Mechanical structure that buries the primary concept
- Exceptions added around a boundary that should have been redesigned
- Silent changes to an existing concept's meaning
