---
title: "LRPT (Longest Remaining Processing Time) | supplycm Algorithm Library"
description: "Plain-English explanation of lrpt_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, lrpt_rule, supply chain, plain english, scheduling"
---

# LRPT (Longest Remaining Processing Time)

> **Call it:** `from supplycm.scheduling import lrpt_rule` · **Level:** Intermediate · **You need:** basic arithmetic only

Parallel-machine priority by remaining workload: the job with the MOST work left goes next. Where LPT sorts fixed jobs at the start, LRPT re-decides as work drains - big remaining jobs keep their machines, so no giant finishes last-minute alone.

**Think of it like this:** A relay team's anchor strategy: keep your strongest (longest) runners on the track continuously - never let the biggest workload sit idle waiting.

## When to reach for it

- Parallel machines where jobs' remaining work changes
- Keeps big jobs flowing so makespan stays tight

## Try it with supplycm

```python
from supplycm.scheduling import lrpt_rule

result = lrpt_rule(remaining_times=[5, 3, 4])
print(result)
```

You should see something like:

```text
0
```

Index 0 wins - the 5-unit workload outranks the others; re-run after each completion and the priority updates itself.

## Check yourself

1. How does LRPT differ from LPT?
2. What's LRPT protecting against?
3. When does SPT-style thinking beat LRPT?

<details>
<summary>Show answers</summary>

1. LPT sorts ONCE by total time; LRPT re-ranks continuously by REMAINING time as jobs progress - a living priority.

2. Big jobs finishing late because small ones kept jumping the queue - longest-remaining first pins big jobs early.

3. When average WAIT matters more than makespan - shortest-remaining serves the most jobs soonest; LRPT serves the makespan instead.

</details>

## Try this now

After 2 units of work, recompute remaining times [3, 3, 4] and verify the priority flips - trace two full dispatch rounds.

---
[← Resource-Constrained Scheduling](resource_constrained_scheduling.md) · [Back to Scheduling library](README.md) · [Machine Utilization →](machine_utilization.md)
