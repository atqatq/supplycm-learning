---
title: "Preemptive SPT (Flow Time) | supplycm Algorithm Library"
description: "Plain-English explanation of preemptive_spt from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, preemptive_spt, supply chain, plain english, scheduling"
---

# Preemptive SPT (Flow Time)

> **Call it:** `from supplycm.scheduling import preemptive_spt` · **Level:** Advanced · **You need:** basic arithmetic only

Computes total flow time when interruptions are allowed: jobs can be paused and resumed as shorter work arrives. Allowing preemption improves average waits dramatically - this quantifies exactly how much that flexibility is worth on your arrival pattern.

**Think of it like this:** A barber who pauses a beard trim for a quick kid's haircut - interrupted, yes, but the shop's average wait improves.

## When to reach for it

- Justifying (or banning) job interruption policies
- Bounding the best possible average flow time with arrivals

## Try it with supplycm

```python
from supplycm.scheduling import preemptive_spt

result = preemptive_spt(arrival_times=[0, 0, 2], processing_times=[4, 2, 3])
print(result)
```

You should see something like:

```text
16.0
```

Total flow time under preemption - compare with a no-preemption schedule to price the flexibility.

## Check yourself

1. What does 'preemption' permit?
2. When is preemption unrealistic?
3. Why does preemption help average waits?

<details>
<summary>Show answers</summary>

1. Pausing a running job to start another, resuming later - time is conserved, attention is flexible.

2. When setups dominate - pausing a furnace or a print run costs real re-setup time that the pure model ignores.

3. It lets tiny arrivals jump the queue instantly instead of waiting behind the current giant - the queue never blocks.

</details>

## Try this now

Compute flow time with and without preemption for [10, 1, 1] all arriving at time 0; explain the gap.

---
[← SRPT (Shortest Remaining Processing Time)](srpt_rule.md) · [Back to Scheduling library](README.md) · [Round-Robin Scheduling →](round_robin_scheduling.md)
