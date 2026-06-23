# sources/ — Raw, Immutable Inputs

This is the ground truth your wiki is built from. Put your project's real material here: specs, design docs, data files, notes, articles, transcripts — anything the agent should reason *from*.

## Rules

- **Read-only.** The agent reads these files; it never edits, moves, or deletes them. If a source is wrong or outdated, that gets noted in the wiki — the source itself stays as-is, so you always know what the wiki was built on.
- **No secrets.** Never put credentials, keys, or private personal data here. Treat everything in this folder as material the agent will read in full.
- **Cite-able.** Every claim in the wiki traces back to a file in here. Give files clear names so citations are meaningful (`spec-v2.md` beats `doc1.md`).

## How material flows

```text
You drop a file here  →  ask the agent to ingest it  →  it appears, summarized
and cross-linked, in wiki/  →  the agent logs the ingest in wiki/log.md
```

Add sources whenever the project grows. Re-run an ingest after you add new material so the wiki stays current.
