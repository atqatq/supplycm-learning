---
title: "Total Completion Time | supplycm Algorithm Library"
description: "Plain-English explanation of total_completion_time from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, total_completion_time, supply chain, plain english, scheduling"
---

# Total Completion Time

> **Call it:** `from supplycm.scheduling import total_completion_time` · **Level:** Beginner · **You need:** basic arithmetic only

The sum of all finishing times - the aggregate time jobs spend in the system. Minimizing it means customers COLLECTIVELY wait least; its champion is the humble SPT rule. This function scores any sequence on that measure.

**Think of it like this:** Total checkout time for a whole queue: minimizing the SUM matters even if one individual waits a bit longer.

## When to reach for it

- Evaluating sequences on throughput-style measures
- Verifying why SPT dominates FCFS on average experience

## Try it with supplycm

```python
from supplycm.scheduling import total_completion_time

result = total_completion_time(sequence=[0, 1, 2], processing_times=[4, 2, 8])
print(result)
```

You should see something like:

```text
24.0
```

The total for this order - reorder smallest-first and watch the total drop; that's SPT's theorem made visible.

## Check yourself

1. Which rule provably minimizes total completion time?
2. Why does finishing short jobs early help everyone?
3. What does this metric ignore that tardiness catches?

<details>
<summary>Show answers</summary>

1. SPT - shortest processing time first, no tie-breaking required.

2. Each unfinished job blocks ALL followers - short jobs early unblock the queue sooner for the collective.

3. Due dates - a sequence can minimize total time and still humiliate the one job with a hard promise.

</details>

## Try this now

Compute totals for FCFS and SPT orders of [3, 1, 4, 1, 5]; express the improvement as a percentage.

---
[← Tardiness Calculation](tardiness_calculation.md) · [Back to Scheduling library](README.md) · [Total Weighted Tardiness →](total_weighted_tardiness.md)
