---
title: "SPT (Shortest Processing Time) | supplycm Algorithm Library"
description: "Plain-English explanation of spt_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, spt_rule, supply chain, plain english, scheduling"
---

# SPT (Shortest Processing Time)

> **Call it:** `from supplycm.scheduling import spt_rule` · **Level:** Beginner · **You need:** basic arithmetic only

Do the quick jobs first. Average waiting time falls dramatically - small tasks stop drowning behind big ones. The mathematically proven champion for minimizing average completion time on one machine, and the best-kept open secret of productive teams.

**Think of it like this:** Answering the one-line email before drafting the report: five tiny wins clear the deck while the giant task waits its turn.

## When to reach for it

- Clearing backlogs where average response time matters
- Any single-server queue with mixed job sizes

## Try it with supplycm

```python
from supplycm.scheduling import spt_rule

result = spt_rule(processing_times=[8, 3, 5, 2, 7])
print(result)
```

You should see something like:

```text
[3, 1, 2, 4, 0]
```

Jobs sorted 2, 3, 5, 7, 8 - the short ones clear instantly; total waiting across all jobs collapses versus FCFS.

## Check yourself

1. What does SPT provably minimize?
2. What's SPT's dark side?
3. How do real shops fix starvation?

<details>
<summary>Show answers</summary>

1. Average (mean) completion time on a single machine - it is optimal for that measure.

2. Starvation: big jobs keep getting pushed back - forever, if small ones keep arriving.

3. Aging rules: jobs get priority as they wait, blending SPT's speed with fairness.

</details>

## Try this now

Compare FCFS vs SPT total waiting on [1, 20, 2, 30, 3]; compute the percentage SPT saves.

---
[← FCFS (First Come, First Served)](fcfs_rule.md) · [Back to Scheduling library](README.md) · [WSPT (Weighted SPT) →](wspt_rule.md)
