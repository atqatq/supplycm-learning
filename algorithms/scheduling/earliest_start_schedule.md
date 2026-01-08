---
title: "Earliest Start Schedule | supplycm Algorithm Library"
description: "Plain-English explanation of earliest_start_schedule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, earliest_start_schedule, supply chain, plain english, scheduling"
---

# Earliest Start Schedule

> **Call it:** `from supplycm.scheduling import earliest_start_schedule` · **Level:** Intermediate · **You need:** basic arithmetic only

Project scheduling's workhorse: each task starts the moment its predecessors finish. Forward through the network, no delays, no cleverness - and the finish time you get is the project's fastest possible completion given the dependencies.

**Think of it like this:** Cooking a multi-dish meal: each step starts the instant its ingredients are ready - no deliberate waiting anywhere.

## When to reach for it

- Baseline project schedules before resource juggling
- Finding the fastest theoretical finish for a dependency network

## Try it with supplycm

```python
from supplycm.scheduling import earliest_start_schedule

result = earliest_start_schedule(durations=[3, 2, 4, 1], predecessors=[[], [0], [0], [1, 2]])
print(result)
```

You should see something like:

```text
[0.0, 3.0, 3.0, 7.0]
```

Start times per task - task 3 waits for both 1 and 2, and the last task's finish is the project's fastest possible date.

## Check yourself

1. What does 'earliest start' assume away?
2. Why is this the fastest possible?
3. How does this feed critical path analysis?

<details>
<summary>Show answers</summary>

1. Resource limits - infinite workers and machines; reality's constraints come later (that's RCPSP).

2. Every task starts as early as physics (dependencies) allows - no calendar slack exists to remove.

3. The finish times reveal which chains are tight - pairs perfectly with slack calculation.

</details>

## Try this now

Compute starts for a 6-task project with two merge points; identify which merge sets the finish date.

---
[← Gantt Chart Data](gantt_chart_data.md) · [Back to Scheduling library](README.md) · [Critical Path Method (CPM) →](critical_path_method.md)
