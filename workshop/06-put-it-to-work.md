# 06 · Put It to Work

Everything so far was practice on pieces. Now point the whole thing at your real capstone project — the engineering work this wiki exists to help you with. There is no toy version; the deliverable is a wiki you will actually keep using.

## The goal

Take a genuine problem from your capstone — a bug you do not understand, a design decision you are stuck on, a body of material you need to make sense of, a system you need to reason about — and use your LLM wiki to work it through, end to end.

## The arc

You will run every pillar at least once:

```text
Ingest    Put the real material into sources/. Let the agent build the wiki.
Direct    Ask grounded questions. Use the lowest rung that works.
Document  Keep both logs current — what you did, and what you learned.
Evaluate  Run your eval set. Trust the answers only after you have tested them.
Learn     Use the agent to actually understand the problem, not just resolve it.
Decide    Make the call. Write down the decision and why, in the project log.
```

## Definition of done

- **A working wiki** on your real problem: sources ingested, pages linked, `index.md` current.
- **A decision or result** you can defend, with the reasoning recorded in `wiki/log.md`.
- **An eval run** showing you tested the wiki's answers, with failures labeled and at least one `AGENTS.md` improvement that came from them.
- **A learning-log entry** in your own words: what you understand now that you did not before, and the next question you would chase.
- **An `AGENTS.md`** that is genuinely yours — edited from experience, not the starter defaults.

## The standard

You are judged on **restraint and honesty**, not cleverness. A plain prompt that solved it beats an elaborate agent that impressed. A wiki that openly marks what it cannot support beats one that confidently fills every gap. The win condition is a small engine you trust — and a clear-eyed account of where you still should not.

## Keep going

The wiki does not end here. As your capstone moves forward, new material goes in `sources/`; the agent keeps the wiki current; the logs keep growing; the eval set keeps it honest. You have built something that compounds: every source you add and every failure you catch makes it more useful and more trustworthy than before.

> Use the lowest rung that works. Document everything. Trust nothing you have not checked.

---

Back to: [Orientation](00-orientation.md) · [the schema](../AGENTS.md)
