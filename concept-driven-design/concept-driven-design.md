# Concept Driven Design (CDD)

Concept Driven Design is an approach to designing software around an explicit set of meaningful concepts before deciding how the code should work.

The goal is **conceptual integrity**: a coherent concept system. The product, codebase, tests, documentation, and team vocabulary tell the same story. Concepts are distinct, their meanings hold, and concept implementations stay aligned with those meanings.

Prefer the **smallest set of distinct concepts that jointly hold**. Integrity comes first. Once the model holds together, do not add concepts for ornamental granularity.

That story is carried less by labels alone than by **concept outline**: what you see when you skim — name, structure, grouping, ordering, and hierarchy of presentation. Names are part of the outline. So are the layout of a function body, the order of members in a type, the arrangement of a file, and the presentation of a module or product surface.

## Key terms

- **Concept** — a named unit of meaning with a clear identity, boundary, responsibilities, relationships, and affordances.
- **Concept system** (also called the **model**) — many concepts and how they relate.
- **Concept implementation** — the code, design, UI, or data that represents a concept.
- **Concept outline** — the visible form that signifies a concept at a glance: name, structure, grouping, ordering, hierarchy of presentation, and related signals. Skim or squint: what main structure remains?
- **Conceptual integrity** — the concept system holds: concepts are distinct and true to their meaning, implementations match those meanings, and the whole is graspable as one model. High conceptual integrity feels simple and light to work with. Low conceptual integrity feels complex and heavy because it adds conginitive load, usually because people must discover and carry exceptions and mismatched meanings.
- **Implementation drift** — the concept implementation no longer matches its named meaning, often through many small changes that each chip away at the concept.
- **Over-conceptualise** — too many concepts for the integrity of the system: locally clear nouns that do not earn their place. Some should merge.
- **Under-conceptualise** — not enough separation: one name holding independent meanings that can change apart. Some should split.

Other words used below (boundary, drift, light, heavy, broken, and so on) keep their ordinary meanings.

## Why concepts matter

Much of a system's felt complexity comes not from its number of lines of code, but from the exceptions people must keep in their head when conceptual integrity is low.

Learning a clear concept is low cost. The heavier cost is remembering every time that concept no longer holds: special cases, legacy paths, "except when…" knowledge, places where the idea was never designed well, and implementations that drift from the meaning they claim to represent.

There is a second cost that is easy to miss. It is easy to invent locally good, finely sliced concepts. Each may be clear on its own. The hard part is that every concept must also be **distinct** from the others and **fit** with them so the whole system coheres. A concept that does not improve the integrity of the system still adds load: another boundary, another relationship, another place for drift.

**Conceptual integrity** protects against both. Build concepts that hold, stay distinct, and compose into one graspable model. Then express that model in the concept outline of the system, from the smallest readable unit up to the largest.

A useful day-to-day test when considering a new concept:

> Does adding this concept increase the integrity of the whole model (clearer boundary, fewer exceptions, less overlap), or only create a nicer local noun?



## What is a concept?

A **concept** is a named unit of meaning. It belongs in the shared mental model first. Its **concept implementation** should then take the simplest form that preserves that meaning.

Examples include:

- Product and domain concepts: `Order`, `Subscription`, `AssessmentResult`
- Meaningful system concepts: `RetryPolicy`, `PaymentAttempt`, `FeatureFlag`

Names such as `Helper`, `Manager`, `Utils`, `data`, and `processData` are warning signs. They usually describe machinery without explaining what it means.

Not every noun deserves a concept, and not every concept needs its own class, file, or database table.

A concept that holds lets someone predict:

- what it represents
- what it can do
- what can happen to it
- where its responsibilities begin and end
- how it relates to other concepts



## Core principles



### 1. Concepts before mechanisms

Name the primary concepts before writing code. If the concepts cannot be explained clearly, the design is not ready.

The concept outline — names, structure, order, and interfaces — should communicate this without requiring someone to reconstruct the meaning from implementation details.

### 2. Prefer the smallest set of distinct concepts that jointly hold

Optimise for a coherent concept system (the model).

Concepts should **hold**: clear identity and boundary, few forced exceptions, implementation aligned with meaning.

They should be **distinct**: not synonyms, not overlapping slices of the same idea, not independently evolving concerns forced into one name.

They should **fit together**: the vocabulary as a whole should be graspable, and each concept should earn its place by improving the integrity of that whole.

Before combining two concepts, ask:

> Could one change without the other?

If yes, keep them separate. Splitting here preserves integrity; under-conceptualising (collapsing distinct meanings into one name) usually reappears later as exceptions people must memorise.

This test applies to meaning, not file count. One concept may require several files, while several tightly related concepts may reasonably share one small module.

### 3. Make the concept outline tell the same story

A concept is not finished when it has a good name. It is finished when a reader can see what it is from the outline of the code and product that express it.

Apply this at every scale:

- **Within a block:** related statements group together; blank lines and ordering separate meaningful steps; the sequence reads as the concept's story, not as an accidental trail of edits
- **Within a type or file:** the primary concept appears first where the language allows (main type, main function or class, primary constants or config), with supporting parts below it; methods, properties, helpers, and nested components follow the concept's structure rather than an arbitrary or purely mechanical order
- **Across modules and surfaces:** directories, modules, APIs, tests, and product flows reveal the same conceptual outline

Prefer a top-down outline when the language makes it natural: the highest-level concept up front so a reader can grasp meaning quickly, then descend for smaller parts and detail. The point is not a rigid house style. It is that hierarchy of meaning should be visible in hierarchy of presentation.

Names, types, and interfaces still matter. They are signals inside the outline. An accurate name in a misleading structure still hides the concept.

Implementation details should support the concept system rather than become the model.

### 4. Apply the same thinking to product design

CDD applies to product UI and features as well as code.

Labels, screens, flows, actions, navigation, and visual hierarchy should make product concepts clear and intuitive. Users should understand what something is, what they can do with it, and where it belongs, including from the outline of the interface, not only from the words on it.

The UI does not need to expose technical concepts or copy internal names literally. User-facing and internal models may use different language for different audiences, but their meanings and relationships should correspond deliberately rather than drift accidentally.

### 5. Evolve concepts explicitly

New work must not silently change what an existing concept means.

When the current model no longer fits:

1. **Align** with the existing concept if it still describes the problem accurately.
2. **Redefine** or split the concept if the underlying meaning has changed.
3. **Document the divergence** if immediate realignment is impractical.

A real redefinition updates the concept wherever its meaning appears, including its outline and implementations. Renaming one variable while preserving a misleading outline is not enough.

## Applying CDD



### 1. Understand the problem

Start with user goals, domain knowledge, product requirements, existing behaviour, and the language people already use. Look for meaningful entities, actions, states, rules, and relationships.

### 2. Inspect the existing model

Before adding anything, identify the concepts and vocabulary already present in the concept system.

Ask:

- Does this change extend an existing concept?
- Is that concept still accurate — does it still hold?
- Would a new concept overlap with one already present?
- Are different names disguising the same idea?
- Is one name being used for several different ideas (under-conceptualised)?
- Would a new concept improve the integrity of the whole model, or only over-conceptualise with a finer local noun?



### 3. Define the proposed model

For each important concept, write a short definition covering:

- what it means
- what it owns
- what it can do
- what it must not do
- how it relates to other concepts
- what could cause it to change

If a concept cannot be described clearly in one or two sentences, its boundary probably needs more work.

### 4. Pressure-test the boundaries

Use the independent-change test between concepts. Combine ideas that genuinely form one meaning. Separate ideas that can evolve independently. Check that the set as a whole is distinct and jointly coherent — neither over- nor under-conceptualised.

Question abstractions that exist only to pass data between technical layers or hide unclear responsibilities.

### 5. Map concepts through the system

Carry the model deliberately into product language, concept implementations, outlines, interfaces, tests, APIs, analytics, and documentation. They need not have identical representations, but they should preserve the same meaning and a recognisable outline.

### 6. Implement a faithful, coherent version

Choose the least elaborate concept implementation that faithfully represents the concepts. Shape the outline so the primary concept is easy to find and its parts read in a meaningful order. Avoid speculative abstractions for future concepts that do not yet exist. Prefer redesigning a weak concept over papering over it with special cases.

### 7. Check conceptual integrity

Before finishing, ask:

- Can each important unit be described in a sentence that matches its name?
- Would someone correctly predict its behaviour from its outline and interface, without reconstructing meaning from scattered details?
- Does the visual structure of the code or surface match the concept's hierarchy (primary idea first, supporting parts after, related steps grouped)?
- Are the concepts distinct, and do they fit together as one model?
- Are independently changing responsibilities mixed together?
- Do product, code, tests, and documentation use a coherent vocabulary and a coherent outline?
- Did the change introduce exceptions to a concept that should have been redesigned or split instead?
- Did it leave the implementation misaligned with the concept's meaning (implementation drift)?
- Did it quietly alter the meaning of an existing concept?
- Does the result feel lighter to work with, or heavier?



## Worked example

Suppose a product sells ongoing access to a programme.

A weak model might put everything in `BillingManager` and `UserData`. Those names reveal little about the product and allow unrelated behaviour to accumulate — under-conceptualised, with a mechanical outline.

A clearer concept system might contain:

- `Plan`: the offer, price, and included access
- `Subscription`: a customer's ongoing agreement to a plan
- `PaymentAttempt`: one attempt to collect payment for a subscription

These concepts are separate because they are distinct and can change independently. A plan's price can change without rewriting an existing subscription. A payment attempt can fail without ending the subscription immediately. Together they form a small coherent model: each holds, none overlaps, and the product story is graspable as a whole.

The same model can appear throughout the product:

- UI: "Your subscription", "Change plan", and "Payment failed", with those ideas given clear visual priority in the outline
- Code: concept implementations organised around plans, subscriptions, and payment attempts, with the primary concept outlined above its supporting parts
- Tests: "subscription remains active during the payment retry period"
- Analytics: events such as `SubscriptionStarted` and `PaymentAttemptFailed`

The representations differ, but the underlying concepts and their outlines remain coherent. That is high conceptual integrity: the system stays light to reason about.

## Common failure modes

- **Low conceptual integrity:** the model no longer holds; the system feels complex and heavy because people must discover and carry exceptions and mismatched meanings
- **Implementation drift:** code, UI, or data that claims a concept but no longer matches its meaning
- **Over-conceptualise:** carving finer concepts that may be locally clear but do not improve the integrity of the whole model
- **Under-conceptualise:** combining independently changing ideas under one name, then paying for it in exceptions
- **Mechanical structure:** organising primarily around controllers, managers, handlers, or utilities instead of concepts
- **Naming without outline:** choosing good names while leaving grouping and order as an accidental edit history
- **Bottom-up presentation:** burying the primary concept under helpers, utilities, or incidental detail so readers must reconstruct meaning from fragments
- **Terminology drift:** using several names for one idea or one name for several ideas
- **Name-only modelling:** giving something a domain-sounding name without a coherent boundary or visible outline
- **UI divergence:** presenting users with a contradictory product model
- **Silent redefinition:** changing a concept's meaning without updating its name, outline, or surrounding model
- **One concept, one file dogma:** confusing conceptual boundaries with a fixed filesystem pattern



## Relationship to other practices

CDD is foundational for meaning: many design best practices are tactics that often follow if conceptual integrity holds. It does not prescribe a programming paradigm or folder structure. Where language and local conventions allow, it favours outlines that present higher-level concepts before their supporting details.

- **Brooks' conceptual integrity** — CDD operationalises this as day-to-day practice (outline, drift, align/redefine, over/under-conceptualise).
- **Domain-Driven Design** — closest cousin for discovering and bounding domain meaning; CDD is thinner and broader (UI, system concepts, outline), and the integrity criterion inside or outside full DDD.
- **Clean Code / readable code** — much of it follows from CDD; tidy code without a coherent outline can still be heavy.
- **SOLID** (esp. SRP) — often derived from distinct concepts and the independent-change test; treat as optional tactics, not the goal.
- **Information hiding / modules** — module boundaries should follow concept boundaries, not layer or folder fashion.
- **Screaming architecture / package by feature** — repo-scale concept outline; structure should express the concept system.
- **Simple Made Easy** (Hickey) — complementary: entanglement vs familiarity; CDD adds integrity as the lever that keeps complex systems light.
- **Separation of concerns / orthogonality** — distinct concepts that can change apart *are* separated concerns; without a concept model, SoC often becomes arbitrary layers.
- **DRY / YAGNI / KISS** — useful slogans CDD disciplines (DRY can collapse concepts; YAGNI curbs over-conceptualising; KISS is "light," which can still be complex).
- **Testing (TDD/BDD)** — complementary: pins behaviour once meanings exist; does not invent a good concept system.
- **Clean/hexagonal architecture** — mechanism patterns that protect a coherent model from frameworks and IO.
- **Design patterns** — downstream mechanisms; use when they implement a concept, not when the pattern replaces one.
- **Product / UX** — UI outline and language should correspond to the concept system (words may differ).
- **Team Topologies / Conway** — related layer: concept boundaries often inform team boundaries; org design has concerns CDD does not cover.

CDD does not replace performance, reliability, security, delivery process, or distributed-systems practice — those are different jobs.

Its practical test is simple:

> Can people discuss the system using a stable, coherent vocabulary of distinct concepts, trust those concepts to hold without a private list of exceptions, then find those same meanings clearly outlined in the product and codebase?

Clean code is not merely tidy code. It is code whose outline accurately communicates what the system means.