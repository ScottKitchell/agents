# rapid-fire

Turns sources (PR reviews, feedback, notes, threads) into a short queue of decisions that genuinely need human judgement, each with context and a recommendation, then works through them with the user one at a time.

## Why it exists

Agents either ask the user about everything or decide everything themselves. Reviews and feedback mix routine fixes, settled questions, and duplicates with a few real trade-offs. This skill does the investigation and filtering so the user spends attention only on judgement calls, and never gets a question without a recommendation.

Design choices:

- **Filter hard.** Anything with a clear fix, a policy answer, or a resolution already in the source stays out of the queue.
- **Stable IDs**, so the user can answer out of order or in bundles.
- **Overview, then one decision at a time**, with an all-at-once view on request. One-at-a-time keeps discussion attached to each decision. Practitioner advice favours batching similar routine choices to cut switching cost; the overview groups related titles for that reason. No controlled evidence favours either, so this is a preference to revisit from real use.
- **Inspection and discussion only.** Agreeing a direction doesn't authorise posting replies, changing code, or merging.

## Iterating

- Test on a real PR with a mix of trivial and genuine review comments. Check the trivial ones are filtered out and each queued card stands on its own without opening the source.
- Check that a source with no real decisions gets "nothing needs you" rather than a manufactured question.
