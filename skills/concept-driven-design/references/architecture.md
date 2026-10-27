# CDD for Architecture and Planning

Architecture is the model at system scale. Boundaries between modules, services, stores, and contracts should follow concept boundaries.

## Plans

Open a tech plan with the model, then the mechanism:

```markdown
## Concepts
- **Subscription**: a customer's ongoing agreement to a Plan. Owns status and renewal. Does not own payment collection.
- **PaymentAttempt**: one try to collect payment for a Subscription. Can fail without ending it.

## Model changes
- New: PaymentAttempt
- Redefined: Subscription no longer ends on first failed payment
- Retired: BillingManager

## Design
...
```

If a concept cannot be stated in one or two sentences, the design is not ready to plan in detail.

## Boundaries

- Organise top-level structure by concept or feature, not by technical layer. `subscriptions/` tells the story; `controllers/`, `services/`, and `utils/` hide it.
- Run the independent-change test on modules and services. Two services that always change and deploy together are one concept split over the wire. One module with unrelated reasons to change is under-conceptualised.
- Treat `common`, `shared`, and `core` packages as suspect. Each item in them belongs to a concept or is genuinely generic infrastructure.
- Question abstractions that only pass data between layers or hide an unclear responsibility.
- Use frameworks and patterns (hexagonal, CQRS, queues) to protect the model, not to replace it.

## Data

- A table or collection should represent one concept. Columns that are only meaningful in some rows, or a `type` field that switches behaviour, usually signal a hidden concept.
- A status enum that mixes independent lifecycles (for example `active`, `payment_failed`, `archived`) is under-conceptualised. Separate the lifecycles.
- When a concept is redefined, migrate the data and names with it. A renamed class over an old column name leaves drift behind.

## Contracts

- Name endpoints, payloads, and events after concepts. Events state concept facts in the past tense: `SubscriptionStarted`, `PaymentAttemptFailed`.
- Keep internal mechanism out of contracts. Consumers should see the concept, not the storage or workflow behind it.
- Different contexts may represent the same concept differently. Map between them deliberately at the boundary rather than letting one context's meaning leak into another.

## Smells

- Layer-first structure as the primary outline
- One name meaning different things in different services
- A "manager", "orchestrator", or "processor" that owns several unrelated concepts
- New services or tables for concepts that do not pass the Fits test
