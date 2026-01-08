---
title: "Job Shop Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of job_shop_schedule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, job_shop_schedule, supply chain, plain english, scheduling"
---

# Job Shop Scheduling

> **Call it:** `from supplycm.scheduling import job_shop_schedule` · **Level:** Advanced · **You need:** basic arithmetic only

The general case: each job has its OWN route through machines, in its own order. Conflicts appear when two jobs want the same machine at once. This resolves them operation-by-operation with a priority pass, returning start/end times for every operation - the classic hard problem of manufacturing.

**Think of it like this:** A kitchen where every dish has its own recipe order - two dishes need the wok at once, and the chef must arbitrate continuously.

## When to reach for it

- Machining shops where products follow different routings
- Understanding why your ERP's scheduling module behaves mysteriously

## Try it with supplycm

```python
from supplycm.scheduling import job_shop_schedule

result = job_shop_schedule(jobs=[[(0, 3), (1, 2)], [(1, 4), (0, 1)]])
print(result)
```

You should see something like:

```text
{(0, 0): [0.0, 3.0], (1, 0): [0.0, 4.0], (0, 1): [4.0, 6.0], (1, 1): [4.0, 5.0]}
```

A dict of (job, machine) -> (start, end) - trace each job's journey and find the machine that became the bottleneck.

## Check yourself

1. Flow shop vs job shop - the essential difference?
2. What makes job shop scheduling famously hard?
3. What's the practical approach for real shops?

<details>
<summary>Show answers</summary>

1. Flow: everyone shares one route. Job shop: routes are personal - that freedom is what makes it brutally hard.

2. Combinatorial explosion plus deadlock risks - optimal solutions exist but finding them scales terribly.

3. Priority dispatching (this function) plus bottleneck focus - perfect optimality is rarely worth the wait.

</details>

## Try this now

Trace both jobs' schedules in the output; identify which machine starved and which collided - then reorder one job's route mentally.

---
[← Makespan (Cmax) Calculation](cmax_calculation.md) · [Back to Scheduling library](README.md) · [Open Shop Scheduling →](open_shop_schedule.md)
