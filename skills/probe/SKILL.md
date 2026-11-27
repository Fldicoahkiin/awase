---
name: probe
description: "Interview the human about a plan until the answers add up to something buildable, one question at a time, each with a recommended answer. Use when a plan has open edges, or when invoked as awase:probe."
---

Before asking, look: read the files, code and material the plan touches. Never ask the human what those files answer.

Ask one question at a time. Each question names the open edge, gives two to four concrete options and what each would change, and your recommendation with its reason. Take terms and boundaries first, then behaviour at the edges (missing input, failure, repetition, conflicting owners, undo), then details.

When a term is vague or used two ways, propose one precise term and use it from then on.

Stop when the answers add up to a definition of done. Write it as a short spec: what is being built, for whom, the decisions and their reasons, what is out of scope, how it will be checked. Save the spec to a file the human names. Work starts from this spec.
