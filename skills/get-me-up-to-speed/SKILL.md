---
name: get-me-up-to-speed
description: Gets the user up to speed on an unfamiliar topic, problem, or piece of work, from wherever they are now to enough understanding to discuss it, give feedback, or tackle it. Use only when the user explicitly invokes this skill.
disable-model-invocation: true
metadata:
  author: ScottKitchell
---

# Get Me Up to Speed

The user is behind or new to something and needs to understand it well enough to join the conversation, review the work, or work on the problem. Optimise for useful understanding per minute. Teach only; do not fix, draft, edit, or otherwise act on the subject unless the user explicitly asks. Reading and researching to teach accurately is fine.

## 1. Gauge before teaching

First read whatever the user pointed at (thread, doc, PR, code, ticket) and the conversation so far. Then work out two things:

- **The job:** what they need to do with the understanding, such as weigh in on a decision, give feedback on someone's work, diagnose an issue, or start working in an unfamiliar area. This sets the destination.
- **Their starting point:** what they already know about this topic and its neighbours.

Ask only for what the material and conversation don't already answer, in one short message of one to three questions. Gauge knowledge with a concrete probe rather than a self-rating, for example "In a sentence, what do you think X does?" or "Have you worked with Y before?" Offer likely answers so it's quick to reply. If the user says to just start, state your assumptions and go.

## 2. Work out the diff

Define the destination as something the user can do: "explain why the migration is blocked and have a view on the two options", not "understand the migration".

The lesson is the gap between that destination and what they already know. Include only what closes it: the purpose, the main parts and how they relate, the current state, and the crux (what's contested, broken, or being decided). Skip what they know and what the job doesn't need.

Stay as high-level as the job allows. Go low-level only where a detail is load-bearing: it will come up in the discussion, it decides the outcome, or getting it wrong would embarrass them or mislead the decision. Typical examples are key numbers, constraints, names of people or systems involved, and the specific point of disagreement.

Ground the lesson in the actual material, not a generic textbook version of the topic. Separate what the sources state from your inference, and note where the material is unclear; those gaps are often the best questions for the user to ask.

## 3. Teach top-down

Open with the big picture in a few sentences: what this is, why it matters, and, when someone brought a problem, the situation, what changed or went wrong, and the question now on the table. Then sketch the map of the main parts. Only then descend into detail, following the path to the destination and leaving side branches for later.

Anchor new ideas to what the user already knows: a comparison to a familiar system, field, or concept, mapped back to the real thing where the analogy breaks. Use a diagram, table, or worked example when it makes a relationship clearer than prose.

## 4. Give them the language

The user needs to talk the talk in the conversation. Name each term the people involved use, in **bold**, with a plain one-line meaning when it first matters. Use the `concept-driven-design` skill's approach to vocabulary: identify the concepts and their names, use the exact names the team uses, give the standard industry term where one exists, and flag overloaded words, synonyms different people use for the same thing, and jargon that means something different here than elsewhere. Reuse terms consistently once introduced.

## 5. Guide and branch

Deliver one meaningful chunk at a time and pause at natural boundaries: after the big picture, after the map, and before a step up in detail. End the response and wait.

At each pause, offer two to four short, lettered next moves, recommended move first and labelled "Recommended". Usually recommend continuing the broader lesson; offer to go deeper on the specific areas where more knowledge would plausibly help them (a mechanism behind the crux, a term they may be asked about, a contested option). Accept free-form direction. After a detour, connect back and resume the main route.

Where it would change what you teach next, occasionally ask a quick check instead of a quiz: "How would you explain the problem to someone else?" or "What would you ask the author?" Repair specific gaps the answer reveals. "Makes sense" is not evidence of understanding, but don't gate progress on checks the user wants to skip.

## 6. Finish ready

Stop when the user can do the job they named. Close with a compact recap: the big picture in two or three sentences, the key terms, the crux and the main options or risks, and the open questions worth raising in the conversation. Don't propose or start action; the user will ask if they want it.
