---
name: realign
description: "Bring an existing codebase, doc set or design that grew by many rounds of agent edits back in line with what it is for now: recover the intent, list what only the history explains, settle with the human what stays, then rebuild in small checked steps. Use for a messy legacy project, a repo full of _v2 files and fallbacks, docs layered with updates, or for /realign."
---

A project built over many sessions keeps the history of how it was made: copies named `_v2` and `_new`, branches that still handle options someone dropped, defensive fallbacks added on request and never removed, comments narrating a refactor, docs with "更新：" sections stacked on top of each other, the same concept under two names because two sessions named it. Each piece made sense in its session. Together they describe the work, not the thing. Realigning means describing the thing again and making the project match that description.

## 1. Recover what it is for now

Build the picture from the strongest evidence first: what the code does when run, the tests, how it is called, what users and the human say it is for. Git history and old conversations are material for understanding why something exists; they are never a reason for it to stay.

Write a short description of the project as it should read to someone meeting it today: what it does, for whom, its main concepts under one name each, its boundaries. Have the human correct it before going further. Use `probe` for the open edges.

## 2. List what only the history explains

Walk the project against that description and list, with locations:

- **Duplicates and versions**: renamed copies, parallel implementations, old and new paths both live.
- **Paths for dropped options**: code, flags, config and tests for behaviour nobody wants any more.
- **Accumulated guards**: fallbacks, retries, swallowed errors and re-validation that exist because someone once asked, not because a caller needs them.
- **One concept, several names**; **several concepts, one name**.
- **Narration**: comments, docs and commit-style notes describing changes instead of the current state.
- **The default look**: generic structure, boilerplate and stock UI that came from the average, not from this project.

For each item, say what evidence shows it is unused or unintended, and what would break if it went.

## 3. Settle what stays

Some items are deliberate. Put the uncertain ones to the human with `decide`: keep, merge, delete, rename. Record each decision with its reason and scope, so the next session does not rebuild what was removed.

## 4. Rebuild in small checked steps

Before changing behaviour, pin it: characterization tests or recorded outputs for what must keep working. Then work in steps that can each be reverted on its own: one rename, one merge, one removal at a time. Run the checks after each step. Rename in place under the domain name; never leave the old and new side by side.

Docs are rewritten from the description in step 1 and the code as it now is, not patched section by section. Use `brief` and a fresh context for them.

History is read too. If the history has not been shared or built on yet, rebuild it so each commit is one change someone reviewing the project would want to see, and the dead ends never appear; then force-push. Once others have pulled or depend on it, leave the history alone and let the next commits carry the cleanup.

## 5. Read it cold

Use `review` on the result: a context that never saw the old project reads the code and docs as a newcomer and marks what still only makes sense with the history.
