---
name: brief
description: "Before producing a deliverable someone else will read — a design, UI copy, marketing copy, README, docs, PR, essay — research its reader and material, turn the conversation into a brief, produce the result in a fresh context that sees only the brief, and review it in another. Use when the conversation holds rejected options, references, earlier drafts or the user's own descriptive words, or when invoked as awase:brief."
---

The conversation is the nearest material, and whatever is nearest ends up in the result: rejected options, earlier drafts, the user's own words translated into headings and labels, a reference's sentences, the default look of the training data. This skill moves the right material close and the rest out of reach.

## 1. Settle the reader and the job

Say who reads or uses the result and what they need from it. If that is unclear, ask with choices instead of making the user write a spec: name the two or three readings the request allows, what each would change, and your pick. Ask only what changes the work; decide routine choices yourself.

For writing, settle one more thing: is the process part of the subject? In a personal essay, a story or a retrospective the experience is what the reader came for, told from inside, in the order that serves them. Everywhere else the process stays out.

## 2. Gather raw material

Collect what only this product, person or project has: real users and their situation, real screenshots, copy, data, code, the user's own assets and stories. End with the common-version list from `awase:research` step 4 if one exists. Use public sources for the field's standards and for what competitors and neighbouring products do. Without raw material the result falls back to the average of what you have seen; for design that now includes the fashionable styles every generated site shares.

If a fact the reader needs is missing, ask the user for it. Do not invent specifics.

## 3. Sort the user's words

Go through what the user said and sort each part:

- **Constraints**: must hold in the result.
- **Purpose**: what the result is for.
- **Feel**: words describing how it should come across ("breathing room", "not too corporate"). Turn these into properties; never place the words themselves in the result.
- **Dropped**: options, drafts and directions turned down. They stay out of the brief entirely.

From a reference, take properties (rhythm, density, hierarchy, how information is ordered), not its sentences, layouts or signature moves. A property written so precisely that it rebuilds the original is the original; describe it one level up.

## 4. Write the brief

The brief carries the reader, the purpose, the facts and raw material, the properties wanted, the constraints, and how the result will be checked. It is written by the same rules as the result: no history, no rejected options, no version labels, no quotes of the user's descriptive words. For prose, add the wording in [reads-as-ai.md](../review/references/reads-as-ai.md) as words to avoid. The common-version list from step 2 stays out of the brief; it goes to the reviewer. Save the brief to a file.

## 5. Produce in a fresh context

Hand the brief to a subagent that sees nothing else. If you cannot start a subagent, write the brief to a file and ask the human to open a new session with only that file. For design or copy, ask for two to four directions that differ in substance, each grown from a different piece of the raw material. Directions differ in substance when each has a different central idea: what the reader sees or does first, and what carries the page. Directions that share one layout and change only palette, type or illustration are one direction. Start each as a quick sketch of the first screen; build a full version only of the ones the user picks.

When the user asks for the agent's own taste or invention, each direction carries a point of view the agent can defend, and the agent says which one it would ship and why.

## 6. Review in another fresh context

A second subagent gets the result, the brief, the reader and the common-version list, nothing of the conversation, and follows `awase:review`. Taste references and lists of overused styles belong here, with the reviewer, not with the producer.

Send the marks and the brief to a new subagent to revise. Then show the user the result, the review marks, and for design the directions to choose between. The user picks.
