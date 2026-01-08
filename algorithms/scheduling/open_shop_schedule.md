---
title: "Open Shop Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of open_shop_schedule from the supplycm Scheduling module, with a runnable Python example and self-check questions."
keywords: "supplycm, scheduling, open_shop_schedule, supply chain, plain english, scheduling"
---

# Open Shop Scheduling

> **Call it:** `from supplycm.scheduling import open_shop_schedule` · **Level:** Advanced · **You need:** basic arithmetic only

Jobs need all machines, but in ANY order - the route is free. The scheduler assigns every (job, machine) visit an order and time. With two machines there is a neat optimal result; beyond that it turns wild. This returns a full feasible itinerary per machine.

**Think of it like this:** A spa day: massage, facial, and sauna in any order you like - the scheduler arranges everyone's itinerary so no room is double-booked.

## When to reach for it

- Testing/inspection flows where operation order is free
- Understanding the scheduling family's spectrum of difficulty

## Try it with supplycm

```python
from supplycm.scheduling import open_shop_schedule

result = open_shop_schedule(processing_times=[[3, 2], [4, 1]])
print(result)
```

You should see something like:

```text
[[[0, 0.0, 3.0], [1, 3.0, 7.0]], [[1, 0.0, 1.0], [0, 3.0, 5.0]]]
```

Each machine's itinerary as (job, start, end) - every job visits both machines exactly once, in whatever order avoids collisions.

## Check yourself

1. What freedom does an open shop give that flow shop doesn't?
2. Why is 2-machine open shop special?
3. What does 'no idle time on both machines simultaneously' imply?

<details>
<summary>Show answers</summary>

1. Operation ORDER per job - the scheduler may permute each job's route to dodge conflicts.

2. Longest-processing-time logic solves it neatly - one of scheduling's rare clean results.

3. The famous Graham bound: makespan can be kept near the natural load limit - open shops are tamer than job shops.

</details>

## Try this now

Verify no job visits two machines at once in the output - then try to find a shorter total yourself.

---
[← Job Shop Scheduling](job_shop_schedule.md) · [Back to Scheduling library](README.md) · [Two-Machine Open Shop →](two_machine_open_shop.md)
