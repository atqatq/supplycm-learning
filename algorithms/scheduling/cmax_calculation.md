---
title: "Makespan (Cmax) Calculation | supplycm Algorithm Library"
description: "Plain-English explanation of cmax_calculation from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, cmax_calculation, supply chain, plain english, scheduling"
---

# Makespan (Cmax) Calculation

> **Call it:** `from supplycm.scheduling import cmax_calculation` · **Level:** Beginner · **You need:** basic arithmetic only

When does the last job finally finish? Cmax - the makespan - is the schedule's total length and the promise you make to the customer. This computes it for any sequence on any machine set. It is the scoreboard every scheduling method plays for.

**Think of it like this:** Marathon finish time: not when the leaders finish - when the LAST runner crosses; that's the event's true duration.

## When to reach for it

- Scoring any schedule before committing to it
- Reporting schedule length to sales and customers

## Try it with supplycm

```python
from supplycm.scheduling import cmax_calculation

result = cmax_calculation(sequence=[0, 1, 2], processing_times=[[3, 2, 2], [4, 1, 3], [2, 2, 1]])
print(result)
```

You should see something like:

```text
12.0
```

One number - the makespan of this order; swap the sequence, recompute, compare. That loop is scheduling.

## Check yourself

1. Makespan vs average completion - what's the difference?
2. Why do sales teams care about makespan?
3. Can two orders share the same makespan?

<details>
<summary>Show answers</summary>

1. Makespan watches the LAST finisher; average watches everyone's experience - sequences can win one and lose the other.

2. It IS the delivery promise - the factory's next free moment starts where makespan ends.

3. Easily - many orders tie on makespan while differing wildly on waits; that's why multiple metrics matter.

</details>

## Try this now

Compute Cmax for 3 orders of the same 4-job instance; note how ties and differences teach you about idle time.

---
[← NEH Heuristic](neh_heuristic.md) · [Back to Scheduling library](README.md) · [Job Shop Scheduling →](job_shop_schedule.md)
