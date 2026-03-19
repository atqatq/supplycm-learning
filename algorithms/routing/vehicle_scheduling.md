---
title: "Vehicle Scheduling (Minimum Fleet) | supplycm Algorithm Library"
description: "Plain-English explanation of vehicle_scheduling from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, vehicle_scheduling, supply chain, plain english, routing & transportation"
---

# Vehicle Scheduling (Minimum Fleet)

> **Call it:** `from supplycm.routing import vehicle_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

How many vehicles does today's timetable actually need? Sort trips by start time and let each vehicle chain compatible trips back-to-back. The answer is the minimum fleet size - buses, trucks, or service vans - that covers the schedule.

**Think of it like this:** A wedding photographer covering ceremonies: sort by start time, hand each camera a chain of events it can reach in sequence - count the cameras needed.

## When to reach for it

- Sizing fleets for fixed trip schedules
- Shift planning where vehicles must chain assignments

## Try it with supplycm

```python
from supplycm.routing import vehicle_scheduling

result = vehicle_scheduling(trips=[(0, 3), (2, 5), (6, 8)])
print(result)
```

You should see something like:

```text
2
```

The minimum number of vehicles - trip 1 can't chain to trip 2 (overlapping), but waits happily for trip 3; the count falls out.

## Check yourself

1. What determines whether two trips can share a vehicle?
2. Why is this deceptively simple here?
3. What does each extra vehicle cost you?

<details>
<summary>Show answers</summary>

1. Non-overlap: the next trip starts at or after the previous one ends (plus deadhead travel, in richer models).

2. With pure time intervals, sorting suffices - real fleets add start/end depots and deadhead times, which complicate chaining.

3. Capital, driver, insurance, parking - the minimum-fleet answer converts directly into budget conversations.

</details>

## Try this now

Add deadhead travel of 1 hour between depots and re-solve; watch the fleet requirement grow and explain why.

---
[← Transshipment Problem](transshipment_problem.md) · [Back to Routing & Transportation library](README.md) · [CVRP Greedy Insertion →](vrp_capacitated_greedy.md)
