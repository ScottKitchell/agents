---
name: concept-driven-design
description: Concept-Driven Design (CDD) for all software planning and building. Use whenever planning, designing, writing, refactoring, or reviewing code, architecture, data models, APIs, or product UI, including small changes and bug fixes. Keeps work organised around a small set of named concepts whose meaning holds, so product, code, tests, and vocabulary tell one story.
---

# Concept-Driven Design

Design around meaning before mechanism. A system feels light when its concepts hold and heavy when people must remember exceptions. On every change, protect and improve **conceptual integrity**.

## Vocabulary

- **Concept**: a named unit of meaning with an identity, boundary, responsibilities, and relationships, such as `Plan`, `Subscription`, or `PaymentAttempt`. Not every noun is a concept, and a concept need not be its own class, file, or table.
- **Model**: the set of concepts and how they relate.
- **Implementation**: the code, data, or UI that represents a concept.
- **Outline**: what a skim reveals: names, grouping, ordering, and hierarchy. Squint at it; the main structure left should be the concept.
- **Conceptual integrity**: every concept holds, is distinct, and fits, and the implementation and outline match the model.
- **Drift**: an implementation gradually diverging from its concept's meaning.
- **Over-conceptualised**: concepts that do not earn their place; merge them. **Under-conceptualised**: one name hiding independent meanings; split it.

## Integrity tests

Apply these to each concept you touch or introduce.

1. **Holds**: Can you state it in one or two sentences that match its name, with no "except when"?
2. **Distinct**: Could it change without its neighbour? If yes, keep them separate. No synonyms for one idea, no single name for two.
3. **Fits**: Does it make the whole model clearer (fewer exceptions, less overlap), or only add a nicer local noun?

Prefer the smallest set of concepts that pass all three. Integrity first, parsimony second.

## Workflow

Scale the depth to the change:

- **Small change inside one concept**: run Find and Check silently. Speak up only if you find drift or a name that no longer fits.
- **Feature or refactor**: name the concepts it touches and how, in a sentence or two, before coding.
- **New subsystem, architecture, or product area**: write a short concept map (meaning, owns, must not do, relationships, what would force it to change) and agree it before building.

Steps:

1. **Find** the existing model in the code, UI, docs, and the user's language. Which concepts does this change touch? Which names are already overloaded or duplicated?
2. **Decide** how the change relates to each concept:
   - **Align** with it when it still describes the problem accurately.
   - **Redefine or split** it when the meaning has genuinely changed, and update it everywhere that meaning appears.
   - **Document the divergence** when realignment is impractical now.
   Never silently change what a concept means. Prefer redesigning a weak concept over adding special cases.
3. **Shape** the outline so the primary concept is visible first, supporting parts follow, and related things sit together. Choose the simplest implementation that preserves the meaning. Add no concepts for futures that do not exist yet.
4. **Check** before finishing: the integrity tests pass, names predict behaviour, product, code, tests, and docs share one vocabulary, no new exceptions or silent redefinitions, and the result is lighter to work with.

## Application guides

Read the guide that matches the work:

- [Architecture and planning](references/architecture.md): tech plans, modules, services, data models, APIs, events.
- [Code](references/code.md): writing, refactoring, and reviewing code and tests.
- [Product and UX](references/product.md): screens, flows, navigation, labels, and copy.

## Share the model

Name concepts in **bold** when introducing or clarifying them, then reuse those exact names. When the user describes something that already has a concept name or a standard industry term, give them that name. When structure changes, explain what each concept now owns and how the pieces relate.
