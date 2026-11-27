---
name: awase
description: "Line up what the human means and what the agent produces: widen the agent's view, settle the decisions with the human, hand the work to a clean context, check it cold. Use when a result carries the conversation inside it (rejected options, version labels, the user's own words pasted into UI or copy, a reference copied), when the human and the agent are talking at different levels of detail, or for /awase."
---

Read the situation, say in one line which of these it is, and run the stages that fit, in this order. Skip a stage that has nothing to do.

| Situation | Stages |
|---|---|
| The human knows what they want but not how the field names it | `terms`, then `probe` |
| The direction is set, the task is shallow | `deepen` |
| The result will fall back to a default look or generic text without real material | `research` |
| Choices are open and some are the human's to make | `probe` for unknowns, `decide` for trade-offs |
| A deliverable for someone else is about to be produced from a long or messy conversation | `brief` |
| A deliverable exists and nobody has read it as its reader would | `review` |
| An existing project grew by many rounds of edits and no longer reads as one thing | `realign` |

The division of work holds in every stage: the agent widens (terms, options, methods, sources, checks) and the human chooses. Ask the human only what no file, experiment or source can answer, one question at a time, with your recommended answer.

When a stage finishes, carry forward its result, not its transcript: the restated request, the decisions with their reasons, the brief. The next stage starts from that.
