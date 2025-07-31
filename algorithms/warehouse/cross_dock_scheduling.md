---
title: "Cross-Dock Scheduling | supplycm Algorithm Library"
description: "Plain-English explanation of cross_dock_scheduling from the supplycm Warehouse module, with a runnable Python example and self-check questions."
keywords: "supplycm, warehouse, cross_dock_scheduling, supply chain, plain english, warehouse"
---

# Cross-Dock Scheduling

> **Call it:** `from supplycm.warehouse import cross_dock_scheduling` · **Level:** Advanced · **You need:** basic arithmetic only

Cross-docking moves goods from inbound trucks straight onto outbound trucks with no storage stop - the warehouse becomes a fast relay station. This schedules trailers onto doors first-come-first-served, which is the baseline every fancier scheme must beat.

**Think of it like this:** An airport transfer desk: bags land from one plane and roll straight onto the next - no locker, no claim, no wait.

## When to reach for it

- High-flow distribution: same SKUs in and out daily
- Time-sensitive goods (fresh food, promo stock) where storage adds cost, not value

## Try it with supplycm

```python
from supplycm.warehouse import cross_dock_scheduling

result = cross_dock_scheduling(inbound_trailers=[(0.0, 30.0), (10.0, 20.0), (25.0, 25.0)], outbound_trailers=[(20.0, 15.0), (45.0, 20.0)], num_doors=2)
print(result)
```

You should see something like:

```text
[[0, 1, 0], [0, 0]]
```

Two door assignment lists come back - inbound and outbound each queued FCFS; mismatches between them are where dwell time hides.

## Check yourself

1. When does cross-docking beat storing?
2. What is the #1 operational failure mode?
3. Why start with FCFS scheduling?

<details>
<summary>Show answers</summary>

1. When inbound and outbound flows match in time and content - the relay only works if the right outbound truck is there.

2. Waiting: inbound goods arrive with no outbound slot - then you are storing anyway, but badly.

3. It is fair, simple, and easy to audit - improve from a clean baseline, not from chaos.

</details>

## Try this now

Simulate 4 inbounds and 3 outbounds by hand on 2 doors; find where goods would 'touch the floor' despite cross-docking.

---
[← Dock Door Assignment](dock_door_assignment.md) · [Back to Warehouse library](README.md)

*New to this topic? Start with the core lesson first: [05_warehouses.md](../../modules/05_warehouses.md).*
