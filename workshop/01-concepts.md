# 01 · Concepts

The working vocabulary of applied AI engineering. Each term gets a plain definition and why it matters for what you are building. Read once now; come back as needed.

> Prefer slides? The [`decks/`](../decks/README.md) are the visual version of this module — start with *Beyond the Answer Machine* ([`05-ai-engineering-v5.html`](../decks/05-ai-engineering-v5.html)) and go deeper with [`01-intro-to-ai-engineering.html`](../decks/01-intro-to-ai-engineering.html).

## The core terms

**LLM (large language model).** A model that predicts the next chunk of text given the text so far. That is the whole trick. It is extraordinarily good at *sounding right*, which is not the same as *being right*. Treat it as a brilliant, fast, confident intern with no memory and no accountability.

**Token.** The unit an LLM reads and writes — roughly a word-piece. Models think and bill in tokens. "Make it cheaper / fit more in" usually means "use fewer tokens."

**Context window.** The total amount of text (in tokens) the model can see at once — your instructions, the conversation, and any files it has read. It is finite. What is not in the window does not exist to the model. Managing the window is most of the skill.

**Prompt.** The instruction you give the model. A good prompt is a **specification**, not a magic phrase: what you want, in what form, with what constraints. Vague prompt, vague output.

**Context.** Everything the model needs to know before it can help: facts, files, goals, constraints, audience. Context is **grounding** — it is the difference between a generic answer and one about *your* project. Deciding what to include (and what to leave out) is judgment, not a data dump.

**Tool / tool-calling.** A capability the model can invoke — read a file, run a command, search the web. A model with tools can act on the world, not just talk about it. Tools are also where the risk lives, so they get boundaries.

**Agent.** An LLM in a loop with tools: it reads, decides, acts, observes the result, and repeats toward a goal. Powerful and worth restraint — *an agent without checks is just automation with confidence.* Every agent here comes with boundaries and verification.

**Harness.** The program that wraps the model, gives it tools, manages context, and runs the loop. In this workshop the harness is **opencode** — it is what lets the agent read your `sources/` and write your `wiki/`.

**Skill.** A reusable, packaged capability — an instruction set the agent can apply on demand (e.g. "ingest a source," "run the eval loop"). Skills let you name a routine once and reuse it instead of re-explaining it every time.

**AGENTS.md.** The schema/rules file that turns a generic agent into *your* disciplined agent. It defines how pages are structured, how sources get ingested, how answers are formatted, and what the agent must never do. Read [`../AGENTS.md`](../AGENTS.md) — it is the heart of this repo.

**Eval (evaluation).** A test of whether output is actually good. Not a vibe — a question with a known-good answer you can check against. Evals are how "I think it works" becomes "I checked, and here is how often it works." See [`04-evaluation-loop.md`](04-evaluation-loop.md).

**Hallucination.** A confident, fluent, *wrong* answer — invented facts, fake citations, plausible nonsense. The default failure of LLMs. The entire discipline of this workshop exists to catch it.

## The three modes

There are three ways to put a model to work. This is a map of the space — not a ranking, and not a guide for action. The point is to recognize which mode you are actually in.

```text
          Prompts   →   Workflows   →   Agents
        ┌─────────────────────────────────────────┐
        │                C O N T E X T              │
        └─────────────────────────────────────────┘
```

- **Prompts** — one-off. You ask, the model answers. A single shot.
- **Workflows** — a fixed, predetermined program: a sequence of steps *you* define in advance, run the same way each time.
- **Agents** — dynamic. The model creates and revises its own steps at runtime to reach a goal.

What changes left to right is *who decides the steps*: you, in the moment (prompt) → a fixed program you wrote ahead of time (workflow) → the model itself, as it goes (agent). The steps shift from fixed to dynamic.

**Context is not one of the three.** It is what the model knows — the facts, files, and goals you put in front of it — and every mode runs on it. A prompt, a workflow, and an agent are each only as good as the context grounding them.

## The restraint rule

> Use the lowest rung that works.

Knowing the space is one thing; choosing where to sit in it is another. Before building a workflow, ask whether a single prompt would do. Before reaching for an agent, ask whether a checklist would. More machinery costs time, money, and risk — so do the *least* that solves the problem, then stop.

## The four failure modes

You will hunt these the entire time. Name them when you catch them.

- **Fluency ≠ correctness.** It sounds right. Check whether it is.
- **Automation bias.** "A machine made it" is not evidence it is true.
- **Anchoring.** The first framing or first source is not automatically the best one.
- **Sycophancy.** A model that agrees with you is not the same as a model that is right.

These four are baked into [`../AGENTS.md`](../AGENTS.md) so the agent self-checks for them too.

---

Next: [02 · Setup](02-setup.md)
