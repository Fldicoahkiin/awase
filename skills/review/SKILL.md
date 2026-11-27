---
name: review
description: "Read a finished deliverable as its reader would, in a context that never saw how it was made, and mark what only makes sense to someone who watched the work. Use before handing over a design, copy, docs, a PR or a piece of writing, or when invoked as awase:review."
---

Give a fresh subagent only three things: the deliverable, who reads it and what they need, and the brief or spec it was made from if there is one. Nothing from the conversation. If you cannot start a subagent, write these three things to a file and ask the human to open a new session with only that file.

Ask it to mark, with location and a rewrite:

- what refers to the making of it: rejected options, earlier versions, the order things were tried, the requester's own words carried in, rules it says it followed;
- what the reader needs and doesn't get;
- terms the reader hasn't been given;
- where it reads as the common version of this kind of thing (use the common-version list from `awase:research` if there is one);
- wording that readers now recognise as generated, from [references/reads-as-ai.md](references/reads-as-ai.md);
- claims stronger than their support.

Send the marks and the brief to a new subagent to revise. The context that holds the conversation does not do the fixing. Check the revised version the same way if the changes were large.
