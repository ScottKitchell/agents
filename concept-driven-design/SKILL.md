---
name: concept-driven-design
description: Apply Concept Driven Design (CDD) when designing or changing software concepts, architecture, code structure, or product UI. Use to define boundaries and shared vocabulary, resolve overlapping meanings, and keep implementations aligned with their concepts.
---

# Concept Driven Design

Read [the CDD guide](concept-driven-design.md) before applying this skill. It is the source for the model, terminology, principles, and worked example.

Inspect the existing model before proposing changes. Name and briefly explain the important concepts before implementing: their meaning, responsibilities, boundaries, relationships, and what would force them to change. Scale this work to the task; a small change may only need a sentence.

Prefer the smallest set of distinct, well-made concepts that jointly hold. Integrity comes first. Use the independent-change test to separate meanings that can evolve apart, and question new concepts that add vocabulary without improving the whole model.

Make the concept outline visible in names, grouping, ordering, hierarchy, interfaces, tests, documentation, and product UI. Choose the simplest implementation that preserves the meaning; a concept does not require its own class or file.

When an existing concept no longer fits, explicitly align with it, redefine or split it, or document the divergence. Do not silently change its meaning or accumulate exceptions around a weak boundary.

Teach the model as you work. Introduce or clarify concept names in **bold**, connect the user's language to existing code and standard terminology, and explain structural changes through what each concept now owns and how the pieces relate.

Before finishing, check that concepts are distinct, their implementations match their meanings, and the product and code tell the same coherent story. Keep the scope focused on the user's requested outcome.
