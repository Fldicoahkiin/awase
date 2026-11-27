# awase

You asked for tomato and eggs, then said no to the braised pork. The PR comes back titled "Tomato and eggs (no braised pork)".

You told the agent the landing page should feel calm, not corporate. The hero now reads "Calm. Not corporate."

You shared a reference for tone. The new copy ends on the reference's last line.

Many sessions in, the repo is full of `_v2` files and fallbacks for options nobody wants.

An agent builds from whatever sits closest to it, and that is the conversation, not the person who will read the result.

awase (合わせ, "bringing two things into line") is a set of agent skills for that gap. A rule that describes the reader helps with content; a list of words readers now recognise helps with wording; neither stops the conversation from leaking in. What does is changing what the agent holds when it writes: the agent brings more terms, options, sources and checks to the table, you choose among them, and a fresh context that sees only the result of those choices does the writing.

## Install

Claude Code:

```
/plugin marketplace add Fldicoahkiin/awase
/plugin install awase@awase
```

Agents that read Agent Skills:

```
npx skills add Fldicoahkiin/awase
```

eta (a workbench for always-on agents that loads Agent Plugins): awase is an [Agent Plugins](https://agent-plugins.org) plugin (`plugin.json` at the repo root). Add `Fldicoahkiin/awase` as a git source in eta's settings, or put a checkout in `~/.eta/plugins/awase/`.

## Requirements

The agent needs to be able to start subagents (fresh contexts) and open web pages. Without subagents, `brief` and `review` write their brief or review packet to a file and ask you to open a new session with only that file.

## Where to start

Run `awase` and let it pick the stages. Call a single command when you already know which stage you are in.

In Claude Code the commands are named `/awase:<name>`, for example `/awase:probe`.

## Commands

**`awase`** — The entry point. Reads the situation and runs the stages that fit.

**`terms`** — Gives the expert terms for what you are describing, the neighbouring fields that solved the same problem, and your request restated in those terms. Output: the restated request.

**`deepen`** — The direction is set, but the task is shallow. Adds what an expert would do, the raw material they would start from, their methods, and what would prove it worked. Output: a rewritten request, shown to you before any work starts.

**`research`** — Before anything gets made. Finds the reader, the specifics only this case has, the field's standards, and what the common version looks like. Output: a sourced report; the common-version list goes to the reviewer only.

**`probe`** — Reads your files first, then asks one question at a time, each with a recommended answer, until the answers add up to a spec. Output: a short spec saved to a file.

**`decide`** — A trade-off that only you can make. Lays it out, then records the decision with its reason, its scope, and when it stops applying. Output: an entry in `decisions.md`.

**`brief`** — Gathers material, sorts your words into constraints, purpose, feel and dropped, and writes a brief. A fresh context produces the result from the brief alone (two to four directions for design or copy), and another reviews it. Output: the result and the review marks.

**`review`** — A context that never saw the work reads it as its reader would and marks what only makes sense to someone who was there, and wording that reads as generated. Output: a list of marks with rewrites.

**`realign`** — For a project that grew through many rounds of agent edits. Recovers what it is for now, lists what only the history explains, settles with you what stays, and rebuilds in small reversible steps. Output: a description of the project, the list of leftovers, and the commits.

## How the pieces hand over

The work happens in more than one context.

- `terms`, `deepen`, `research`, `probe` and `decide` widen what is on the table and get your choices.
- `brief` turns those choices into the only thing the producing context sees. It starts fresh, without the conversation.
- `review` runs in another context that never saw the work, with the common-version list from `research`. Its marks go to a new context to revise.

The producing context sees only the brief.

## What it draws on

- Linda Flower, [Writer-Based Prose](https://doi.org/10.58680/ce197916016) (1979): writers draft in the order they thought, and a second pass turns it toward the reader. `brief` and `review` make that second pass a separate context.
- Herbert Clark on common ground, and the curse of knowledge (Camerer, Loewenstein & Weber, 1989): once you know something, it is hard to write as someone who doesn't. The agent's "knowledge" is its context; a fresh one doesn't have the curse.
- Paul Grice's maxim of quantity: saying something implies it matters. "No braised pork" tells the reader pork was on the table.
- Louis Kaplow, [Rules versus Standards](https://doi.org/10.2307/1372840) (1992): a standard ("write for the reader who wasn't there") reaches cases a list of rules never named, which is why awase describes the reader for content and keeps word lists for wording.
- Anthropic's [Claude Code best practices](https://code.claude.com/docs/en/best-practices): let the agent interview you into a spec, then build from it in a fresh session; a fresh reviewer helps because it hasn't seen your reasoning.
- Kirk et al., [Understanding the Effects of RLHF on LLM Generalisation and Diversity](https://arxiv.org/abs/2310.06452) (ICLR 2024): tuned models give narrower outputs, which is where the default look comes from. `research` brings in material the average doesn't have.
- Shape Narrative, [设计规范为什么会失效？](https://mp.weixin.qq.com/s/C3tmg9gJ1DtSHzla6KwfVg): in design teams, a one-off exception becomes the next template unless its reason, scope and end date are written down. `decide` records exactly those.
- Matt Pocock's [grill-me](https://github.com/mattpocock/skills), GitHub's [Spec Kit](https://github.github.com/spec-kit/) and obra's [Superpowers](https://github.com/obra/superpowers) showed that asking before building works; awase adds the hand-off to a clean context and the cold read at the end.

## License

MIT
