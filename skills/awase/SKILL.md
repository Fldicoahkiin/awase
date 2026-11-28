---
name: awase
description: "Line up what the human means and what the agent produces: widen the agent's view, settle the decisions with the human, hand the work to a clean context, check it cold. Use when a result carries the conversation inside it (rejected options, version labels, the user's own words pasted into UI or copy, a reference copied), when the human and the agent are talking at different levels of detail, or when invoked as awase:awase."
---

Read the situation, say in one line which of these it is, and run the stages that fit, in this order. Skip a stage that has nothing to do.

| Situation | Stages |
|---|---|
| The human knows what they want but not how the field names it | `awase:terms`, then `awase:probe` |
| The direction is set, the task is shallow | `awase:deepen` |
| Material is missing and nothing is being produced yet | `awase:research` |
| Choices are open and some are the human's to make | `awase:probe` for unknowns, `awase:decide` for trade-offs |
| A deliverable for someone else is about to be produced from a long or messy conversation | `awase:brief`; it gathers material, produces and reviews, so skip separate `research` and `review` |
| A deliverable already exists and nobody has read it as its reader would | `awase:review` |
| An existing project grew by many rounds of edits and no longer reads as one thing | `awase:realign` |

The division of work holds in every stage: the agent widens (terms, options, methods, sources, checks) and the human chooses. Ask the human only what no file, experiment or source can answer, one question at a time, with your recommended answer.

Every stage runs on reading and writing files alone. Subagents, web search and a browser make a stage faster or cleaner; when one is missing, take the fallback the stage names, say so in a line, and keep going. Reading, searching, running read-only commands and writing drafts need no go-ahead. Questions to the human are for choices that are theirs and for actions that reach outside the machine.

When a stage finishes, carry its result into the next one: the restated request, the spec, the decisions with their reasons, the research report, the brief. Save each to a file the human names, so a later session can start from it.
