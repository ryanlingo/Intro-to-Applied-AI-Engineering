# 02 · Setup

Get your tools working before you do anything else, so you never lose a session fighting your environment.

You need three things: an **agent harness** (opencode), a **provider key** (the model behind it), and an **editor** (to read and browse your wiki).

## 1. opencode — your agent harness

[opencode](https://opencode.ai) is the program that runs the agent: it reads your `sources/`, writes your `wiki/`, and follows `AGENTS.md`. Install it per the instructions on its site, then open this repo's folder with it.

opencode reads `AGENTS.md` automatically. That file is what makes the agent behave like a wiki maintainer instead of a generic chatbot.

## 2. A provider key and a spend cap

The agent talks to a model through a provider API key. Two rules before you run anything:

- **Use a capable model.** This work rewards a strong reasoning model; a weak one will cut corners and hallucinate more.
- **Set a hard spend cap with your provider first.** Agent loops and eval runs can spend real money. Set the cap before your first run, not after a surprise bill.

## 3. Choose an editor: VS Code or Obsidian

You will look at your wiki constantly. Pick the editor that fits how you think. Both work — this is preference, not correctness.

| | **VS Code** | **Obsidian** |
|---|---|---|
| Best when | Your project is code, or lives near a terminal and Git | Your project is knowledge, notes, docs, research |
| Strengths | Integrated terminal, Git, runs opencode inline, great for editing code and config | Beautiful Markdown browsing, backlinks, graph view of how pages connect, fast navigation |
| Markdown wiki feel | Functional | Excellent — built for exactly this |
| Tradeoff | Markdown browsing is plain | No built-in terminal/Git; you run opencode alongside it |

**Recommendation:** if your project is primarily *code*, use VS Code. If it is primarily *knowledge you want to navigate and connect*, use Obsidian and point a vault at this repo's folder. Many people run both — VS Code for the agent and Git, Obsidian to *read* the wiki and see its graph.

## 4. Keep checkpoints

Your wiki and your `AGENTS.md` will evolve. Never lose a known-good state. If you use Git, these cover almost everything:

```bash
git status
git diff
git add .
git commit -m "checkpoint"
git restore path/to/file
```

If you do not use Git, keep dated copies before big changes. The skill is "I can always roll back," not "I use Git."

## Safety rules

```text
Never paste secrets or private data into a prompt or a source file.
Checkpoint before letting the agent make changes.
Review every change before you accept it.
Prefer small, reviewable steps.
Give the agent narrow authority — let it own wiki/, not your whole machine.
```

## Smoke test

With opencode open on this repo, ask the agent:

> Read AGENTS.md and tell me, in your own words, what your job is in this repo and what you are not allowed to touch.

If it answers that it maintains `wiki/`, follows the schema, and must never edit `sources/`, your setup works. If not, fix the setup before moving on.

---

Next: [03 · Document & Wiki](03-document-and-wiki.md)
