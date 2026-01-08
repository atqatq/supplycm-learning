---
title: "WSPT (Weighted SPT) | supplycm Algorithm Library"
description: "Plain-English explanation of wspt_rule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, wspt_rule, supply chain, plain english, scheduling"
---

# WSPT (Weighted SPT)

> **Call it:** `from supplycm.scheduling import wspt_rule` · **Level:** Intermediate · **You need:** basic arithmetic only

SPT with money on the table: order jobs by processing time DIVIDED BY weight (importance/profit). A 10-minute job worth 1,000 beats a 2-minute job worth 5. It is the proven optimal rule for weighted completion time - scheduling by value density.

**Think of it like this:** A taxi driver choosing fares: a short airport run at premium price can outrank a long cheap one - value per hour of driving decides.

## When to reach for it

- Jobs with different profit or penalty weights
- Any 'which order maximizes value delivered' question

## Try it with supplycm

```python
from supplycm.scheduling import wspt_rule

result = wspt_rule(processing_times=[10, 2, 5], weights=[100, 3, 10])
print(result)
```

You should see something like:

```text
[0, 2, 1]
```

Ordering by weight-per-time: the 10-minute high-value job leads; the tiny but worthless job trails despite its speed.

## Check yourself

1. What ratio does WSPT rank by?
2. WSPT is optimal for which measure?
3. All weights equal - what does WSPT become?

<details>
<summary>Show answers</summary>

1. Processing time over weight - equivalently, weight per unit of machine time; highest density first.

2. Total weighted completion time - literally the best possible order for that objective.

3. Plain SPT - the special case where every job matters equally.

</details>

## Try this now

Schedule 4 jobs with profits [500, 50, 200, 10] and times [20, 2, 10, 1]; verify WSPT's order maximizes weighted value.

---
[← SPT (Shortest Processing Time)](spt_rule.md) · [Back to Scheduling library](README.md) · [EDD (Earliest Due Date) →](edd_rule.md)
