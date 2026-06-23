# 03 · Document & Wiki

This is the core of the workshop: you turn this repo into a living LLM wiki for your own project, and you start the documentation habit that keeps it honest.

## The wiki pattern

Instead of asking the model questions from memory, you give it a folder of *your* material and let it build and maintain a knowledge base on top. Three layers:

```text
Sources   sources/   Raw material. The agent READS, never edits.
Wiki      wiki/       Pages the agent WRITES and keeps current.
Schema    AGENTS.md   The rules the agent follows.
```

Why Markdown? A `.md` file opens in any editor, on any system, with no vendor lock-in. Your knowledge does not depend on a company staying in business or an app keeping a feature. It is yours, in plain text, forever.

## Document everything — two tracks

"Document everything, always" is the rule. But there are two different things worth documenting, so you keep **two logs**:

| Track | File | Captures | Answers |
|---|---|---|---|
| **Project** | [`wiki/log.md`](../wiki/log.md) | What was done, what changed, decisions and why, what is open | *What happened to the work?* |
| **Learning** | [`wiki/learning-log.md`](../wiki/learning-log.md) | What *you* understood, in your own words; aha-moments; open questions | *What did I figure out?* |

The project log is the memory of the work. The learning log is the memory of *you getting smarter* — and it is what makes module [05](05-learning-with-ai.md) work. `AGENTS.md` instructs the agent to keep both: it appends to the project log after work, and prompts you for a learning entry whenever it teaches you something.

## Hands-on: build your wiki

Do this on real material from your own project.

**Step 1 — Add sources.** Put two or three real files into `sources/` — a spec, a design doc, some data, an article, meeting notes. See [`sources/README.md`](../sources/README.md) for the rules.

**Step 2 — Ingest.** Ask the agent:

> Ingest the files in sources/. For each one, create a summary page in the wiki and extract the key concepts and entities into their own pages, with source citations. Then update wiki/index.md and log what you did.

**Step 3 — Inspect.** Open `wiki/index.md` and the new pages in your editor. Check: does every claim cite a source? Did it mark anything unverified? If you use Obsidian, look at the graph — does the structure match how the project actually connects?

**Step 4 — Ask a grounded question.** Ask something only your sources can answer:

> Based only on the sources, what does the spec say about X — and what does it leave unspecified?

A good answer cites source files and openly names the gaps. An answer that confidently fills gaps it cannot support is a **hallucination** — note it; you will catch this kind of thing systematically in the next module.

**Step 5 — Check the logs.** Confirm `wiki/log.md` got an entry. Add your first `wiki/learning-log.md` entry in your own words: what is the wiki pattern, and why plain Markdown?

## What you should have now

- Real sources ingested into a linked set of wiki pages.
- A current `index.md`.
- Both logs started.

If the agent edited a file in `sources/`, stop and tighten `AGENTS.md` — `sources/` is read-only. That kind of fix-the-rules move is exactly how you train your agent.

---

Next: [04 · Evaluation Loop](04-evaluation-loop.md)
