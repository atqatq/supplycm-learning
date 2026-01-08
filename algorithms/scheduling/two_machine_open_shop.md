---
title: "Two-Machine Open Shop | supplycm Algorithm Library"
description: "Plain-English explanation of two_machine_open_shop from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, two_machine_open_shop, supply chain, plain english, scheduling"
---

# Two-Machine Open Shop

> **Call it:** `from supplycm.scheduling import two_machine_open_shop` · **Level:** Advanced · **You need:** basic arithmetic only

The tamed case of open shop: two machines, any operation order, and a clean optimal construction - find each machine's biggest job, keep it first on its home machine, sequence the rest around it. This returns the optimal order directly.

**Think of it like this:** Two barbers and clients needing both chairs in any order: seat the client who'll monopolize a chair first, and the rest falls into place.

## When to reach for it

- Two-stage operations where order per job is free
- Teaching how the right structure dissolves complexity

## Try it with supplycm

```python
from supplycm.scheduling import two_machine_open_shop

result = two_machine_open_shop(processing_times=[(3, 2), (4, 1), (1, 2)])
print(result)
```

You should see something like:

```text
[2, 0, 1]
```

An optimal job order - the makespan lands at the theoretical floor: total load of the busier machine, no idle time wasted.

## Check yourself

1. What is the makespan lower bound here?
2. Why does the biggest single job anchor the schedule?
3. What breaks the elegance at 3+ machines?

<details>
<summary>Show answers</summary>

1. The larger of the two machines' total loads - you cannot finish faster than the busier machine works.

2. It risks idling its opposite machine - placing it first lets the other machine feed during its reign.

3. Interactions multiply - the clean construction no longer guarantees optimality; heuristics return.

</details>

## Try this now

Compute both machines' loads for the example; verify the resulting makespan equals the bigger load exactly.

---
[← Open Shop Scheduling](open_shop_schedule.md) · [Back to Scheduling library](README.md) · [Gantt Chart Data →](gantt_chart_data.md)
