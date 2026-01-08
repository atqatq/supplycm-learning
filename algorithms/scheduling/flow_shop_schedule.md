---
title: "Flow Shop Schedule | supplycm Algorithm Library"
description: "Plain-English explanation of flow_shop_schedule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, flow_shop_schedule, supply chain, plain english, scheduling"
---

# Flow Shop Schedule

> **Call it:** `from supplycm.scheduling import flow_shop_schedule` · **Level:** Intermediate · **You need:** basic arithmetic only

All jobs pass through the same machine sequence (cut, then weld, then paint). This schedules them and returns the order plus makespan. With 2 machines, pair it with Johnson's Rule; with more, it evaluates whatever order you feed it.

**Think of it like this:** An assembly line buffet: every dish visits the same stations in the same order - the question is only who goes first.

## When to reach for it

- Production lines with a fixed stage sequence
- Comparing candidate orders on real makespan

## Try it with supplycm

```python
from supplycm.scheduling import flow_shop_schedule

result = flow_shop_schedule(processing_times=[[3, 2, 2], [4, 1, 3]])
print(result)
```

You should see something like:

```text
[[0, 1], 11.0]
```

An order and its makespan - feed it a Johnson-ordered sequence versus FCFS and watch the gap.

## Check yourself

1. What is a flow shop, formally?
2. What is makespan?
3. Why do more machines make this hard?

<details>
<summary>Show answers</summary>

1. All jobs share one routing - same machines, same order; only the sequence is free.

2. The moment the LAST job finishes - the schedule's total length and the factory's promise to the customer.

3. Idle patterns compound - with 3+ machines, no simple rule is optimal; the problem turns famously difficult.

</details>

## Try this now

Compute makespan for two different orders on 3 jobs x 3 machines; identify the idle-time pattern that made the difference.

---
[← Johnson's Rule (2-Machine Flow)](johnsons_rule.md) · [Back to Scheduling library](README.md) · [NEH Heuristic →](neh_heuristic.md)
