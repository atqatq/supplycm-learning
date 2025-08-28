---
title: "Capacity Requirements Planning (CRP) | supplycm Algorithm Library"
description: "Plain-English explanation of capacity_requirements_planning from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, capacity_requirements_planning, supply chain, plain english, mrp & production planning"
---

# Capacity Requirements Planning (CRP)

> **Call it:** `from supplycm.mrp import capacity_requirements_planning` · **Level:** Advanced · **You need:** basic arithmetic only

CRP takes MRP's planned orders and pushes them through routings - each item's work centers and times - to compute the load on EVERY work center, period by period. Where RCCP checks a few vital signs, CRP gives the full stress test before execution.

**Think of it like this:** A full medical panel instead of checking just blood pressure: every station's workload examined, week by week.

## When to reach for it

- Detailed feasibility checks before releasing planned orders
- Finding which specific work center and week will overload first

## Try it with supplycm

```python
from supplycm.mrp import capacity_requirements_planning

result = capacity_requirements_planning(planned_orders={0: [100, 150, 120]}, routing={0: [(0, 0.5), (1, 1.0)]}, capacities=[80, 160])
print(result)
```

You should see something like:

```text
{0: [50.0, 75.0, 60.0], 1: [100.0, 150.0, 120.0]}
```

Load per work center per period comes back - work center 1 peaks at 150 against 160 capacity, close enough to watch but feasible.

## Check yourself

1. What inputs does CRP need beyond MRP?
2. CRP shows an overload 4 weeks out. Best responses?
3. Why does CRP sometimes load 'past' work centers unnecessarily?

<details>
<summary>Show answers</summary>

1. Routings (which work centers, how long per unit) and each center's capacity.

2. Shift planned orders earlier (pre-build), add capacity (shifts/overtime), or re-plan the orders - all cheap NOW, costly later.

3. Planned orders include queued work - mature setups subtract past-due portions or they double count.

</details>

## Try this now

Add a second item sharing work center 1 and identify the first period where combined load breaks capacity.

---
[← Quantity Discount Lot Sizing](quantity_discount_mrp.md) · [Back to MRP & Production Planning library](README.md) · [Demand Time Fence →](demand_time_fence.md)
