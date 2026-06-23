# 04 · Evaluation Loop

A wiki you cannot trust is worse than no wiki — it is confident misinformation. This module makes trust something you *test*, not something you hope for. You stand up an evaluation loop and run it.

## The loop

```text
Observe  →  Label failures  →  Build evals  →  Improve  →  Re-test
```

- **Observe.** Collect real outputs from your wiki. Read them critically.
- **Label failures.** When an answer is wrong, ungrounded, or misleading, name *what* went wrong and *why*.
- **Build evals.** Turn failures into reusable tests: a question plus the known-good answer.
- **Improve.** Fix the cause — usually a sharper `AGENTS.md` rule, sometimes a better source page.
- **Re-test.** Run the evals again. Did the fix work? Did it break anything else?

This is a loop, not a one-time check. Every failure you catch makes the next version of your wiki more trustworthy.

## Why this beats "looks good to me"

"Looks good" is fluency talking — the failure mode that fools everyone. An eval set turns a vibe into a number: *of my ten test questions, the wiki gets eight grounded and right.* Now you know where you stand, and you can prove an improvement instead of guessing at one.

## Hands-on: build your eval set

Use [`wiki/evals.md`](../wiki/evals.md) — it has the format and a worked example.

**Step 1 — Write 5–10 questions** your wiki *should* answer well from the sources. Mix easy ("what does the spec say about X?") with hard ("where do two sources disagree?"). For each, write the known-good answer yourself, from the sources.

**Step 2 — Run them.** Ask the agent each question in a fresh context. Record the answer next to your known-good one.

**Step 3 — Label failures.** For each miss, mark the failure type:

```text
[ ] ungrounded — claimed something no source supports (hallucination)
[ ] wrong — contradicted by a source
[ ] incomplete — missed something the sources cover
[ ] anchored — over-relied on one source, ignored another
[ ] sycophantic — agreed with a leading question instead of the evidence
```

**Step 4 — Improve.** Most fixes are edits to `AGENTS.md` ("always cite the source file"; "when two sources conflict, list both"). Make the smallest change that addresses the cause.

**Step 5 — Re-test.** Re-run the failed questions. Log the before/after in `wiki/log.md`.

## Evaluate your learning too

The loop is not only for the wiki. Point it at yourself:

- Pick a concept you have ingested. Explain it out loud or in writing *without looking*.
- Ask the agent to check your explanation against the sources and label *your* failures — what you got wrong, what you skipped.
- Record the corrected version in [`wiki/learning-log.md`](../wiki/learning-log.md).

Same loop — observe, label, improve, re-test — applied to your own understanding. That is the bridge to the next module.

## What you should have now

- An eval set in `wiki/evals.md` with known-good answers.
- One full loop run, with failures labeled and at least one `AGENTS.md` improvement.
- A before/after entry in the project log.

---

Next: [05 · Learning with AI](05-learning-with-ai.md)
