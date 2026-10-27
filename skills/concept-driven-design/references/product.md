# CDD for Product and UX

Users meet the model through labels, screens, flows, and actions. They should understand what something is, what they can do with it, and where it belongs, from the interface's outline as well as its words.

## User-facing concepts

- Design the user's model first: the few concepts the product is about from their point of view.
- User-facing names may differ from internal ones, but the correspondence must be deliberate. Keep an explicit mapping when they differ (for example, internal `Enrollment` is "Your programme" in the UI).
- Do not expose technical concepts users do not need.
- Use one name per idea across screens, notifications, emails, help content, and support. Do not call the same thing a "plan", "programme", and "course".

## Outline

- Visual hierarchy should mirror concept hierarchy. The primary concept and its main action dominate; supporting detail recedes.
- Each screen or area should be clearly about one concept or one job. Navigation should reflect the model, not the org chart or the database.
- Group related controls and information together. Separate things that change independently.

## Actions

- Phrase actions as verbs on concepts: "Pause subscription", "Change plan". Generic actions such as "Manage" or "Settings" often hide unclear concepts.
- Show state in the concept's own terms: "Payment failed, retrying in 3 days" rather than a raw status code.

## Adding features

- Before adding a screen, tab, or noun, ask where the feature belongs in the existing model. Most features extend an existing concept.
- Apply the integrity tests. A near-duplicate feature is over-conceptualised. A settings page that collects unrelated options is under-conceptualised.
- Modes or toggles that change what a screen means usually hide a second concept.

## Smells

- Contradictions between what the UI says and what the system does
- Several labels for one thing, or one label for several things
- Junk-drawer screens such as "More" or "Settings" holding unrelated concepts
- Primary actions buried under secondary ones
