---
name: get-me-up-to-speed
description: Gets the user up to speed on an unfamiliar topic, problem, or piece of work, from a single issue to a whole field, from wherever they are now to enough understanding to discuss it, give feedback, or tackle it. Use only when the user explicitly invokes this skill.
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

A broad topic ("the state of AI") has no natural end, so pin down the job before planning. If there's no particular use, the destination is a **working overview**: being able to follow and join conversations about it, knowing the main parts, where things stand, the big open questions, and the key terms.

Ask only for what the material and conversation don't already answer, in one short message of one to three questions. Gauge knowledge with a concrete probe rather than a self-rating, for example "In a sentence, what do you think X does?" or "Have you worked with Y before?" Offer likely answers so it's quick to reply. If the user says to just start, state your assumptions and go.

## 2. Work out the diff

Define the destination as something the user can do: "explain why the migration is blocked and have a view on the two options", not "understand the migration".

The lesson is the gap between that destination and what they already know. Include only what closes it: the purpose, the main parts and how they relate, the current state, and the crux (what's contested, broken, or being decided). Skip what they know and what the job doesn't need.

Stay as high-level as the job allows. Go low-level only where a detail is load-bearing: it will come up in the discussion, it decides the outcome, or getting it wrong would embarrass them or mislead the decision. Typical examples are key numbers, constraints, names of people or systems involved, and the specific point of disagreement.

Plan the smallest route that reaches the destination: usually one stop for a narrow question and no more than five for a broad topic, each one meaningful chunk that unlocks something specific. Show the route as a numbered list in the first teaching response, with what each stop unlocks. Everything off the route is optional depth, offered at checkpoints rather than taught by default.

Ground the lesson in the actual material, not a generic textbook version of the topic. For fast-moving topics, check current sources and say how recent the picture is rather than relying on training data. Separate what the sources state from your inference, and note where the material is unclear; those gaps are often the best questions for the user to ask.

## 3. Teach top-down

The first stop is always the big picture and the map. Open with a few sentences on what this is, why it matters, and, when someone brought a problem, the situation, what changed or went wrong, and the question now on the table. Then sketch the main parts and how they relate. Later stops descend into detail along the route.

Anchor new ideas to what the user already knows: a comparison to a familiar system, field, or concept, mapped back to the real thing where the analogy breaks. Use a diagram, table, or worked example when it makes a relationship clearer than prose.

## 4. Give them the language

The user needs to talk the talk in the conversation. Name each term the people involved use, in **bold**, with a plain one-line meaning when it first matters. Use the `concept-driven-design` skill's approach to vocabulary: identify the concepts and their names, use the exact names the team uses, give the standard industry term where one exists, and flag overloaded words, synonyms different people use for the same thing, and jargon that means something different here than elsewhere. Reuse terms consistently once introduced.

## 5. Guide and branch

Deliver one stop at a time, then end the response and wait. Every checkpoint is an exit: start it with one line on what the user can now do and how many stops remain.

Then offer two to four short, lettered next moves, recommended move first and labelled "Recommended". Usually recommend the next stop; offer to go deeper on the specific areas where more knowledge would plausibly help them (a mechanism behind the crux, a term they may be asked about, a contested option); always include "Stop here". If the harness has a tool for asking the user a multiple-choice question, present the moves with it after writing out the stop's content; otherwise list them as text. Accept free-form direction. Keep a deeper dive to one stop's worth unless they ask for more, then connect back and resume the route. If they change the job, revise the remaining route and show it.

Where it would change what you teach next, occasionally ask a quick check instead of a quiz: "How would you explain the problem to someone else?" or "What would you ask the author?" Repair specific gaps the answer reveals. "Makes sense" is not evidence of understanding, but don't gate progress on checks the user wants to skip.

## 6. Finish ready

Finish when the route is complete or the user chooses to stop. Close with a compact recap: the big picture in two or three sentences, the key terms, the crux or big open questions with the main options or risks, and the open questions worth raising in the conversation. If they stopped early, add one line on what the remaining stops would have covered. Don't propose or start action; the user will ask if they want it.
