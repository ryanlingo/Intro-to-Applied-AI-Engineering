# Evals

The test set that keeps this wiki honest. Each eval is a question your wiki *should* answer well, plus the **known-good answer** you wrote yourself from the sources. You run them, compare, label failures, improve `AGENTS.md`, and re-test. See [workshop module 04](../workshop/04-evaluation-loop.md).

## Eval format

```text
### Q1: the question
- Known-good: the answer you verified from the sources, and which source(s) it comes from
- Last result: [pass / fail] — what the wiki actually answered
- Failure type: ungrounded / wrong / incomplete / anchored / sycophantic
- Fix: the AGENTS.md change (or source fix) you made in response
```

## Failure types

```text
ungrounded   claimed something no source supports (hallucination)
wrong        contradicted by a source
incomplete   missed something the sources cover
anchored     over-relied on one source, ignored another
sycophantic  agreed with a leading question instead of the evidence
```

---

## Worked example (replace with your own)

### Q1: What does the spec say about rate limiting, and what does it leave unspecified?
- Known-good: spec defines a 100 req/min cap per key (source: sources/spec-v2.md) but does not specify behavior on overflow — that is unspecified.
- Last result: _not run yet_
- Failure type: _—_
- Fix: _—_

_Add 5–10 of your own questions before your first run. Mix easy recall with hard "where do sources disagree?" questions._
