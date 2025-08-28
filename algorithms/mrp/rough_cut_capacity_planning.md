---
title: "Rough-Cut Capacity Planning (RCCP) | supplycm Algorithm Library"
description: "Plain-English explanation of rough_cut_capacity_planning from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, rough_cut_capacity_planning, supply chain, plain english, mrp & production planning"
---

# Rough-Cut Capacity Planning (RCCP)

> **Call it:** `from supplycm.mrp import rough_cut_capacity_planning` · **Level:** Intermediate · **You need:** basic arithmetic only

Before trusting a production plan, RCCP asks: can our key resources actually DO this? Multiply planned quantities by per-unit resource needs, compare with capacities, and get the load per resource. Overloads appear here - on paper - instead of on the shop floor later.

**Think of it like this:** Checking the moving truck's capacity against your furniture list BEFORE loading day - not discovering the sofa doesn't fit at midnight.

## When to reach for it

- Validating S&OP production plans against key work centers
- Deciding between overtime, pre-build, or demand smoothing

## Try it with supplycm

```python
from supplycm.mrp import rough_cut_capacity_planning

result = rough_cut_capacity_planning(production_plan=[100, 150, 120], resource_utilization=[[0.5, 0.5, 0.5], [1.0, 1.0, 1.0]], capacities=[100, 160, 160])
print(result)
```

You should see something like:

```text
[0.4405, 0.881]
```

Utilization ratio per resource - resource 2 runs at 150% in period 2, an overload you can fix now by pre-building or moving volume.

## Check yourself

1. RCCP vs detailed CRP - difference?
2. Resource load is 120% for two periods. Options?
3. Which resources belong in an RCCP check?

<details>
<summary>Show answers</summary>

1. RCCP checks a FEW critical resources roughly; CRP schedules every work center precisely.

2. Pre-build earlier, add shifts, outsource, or level the plan - RCCP exists to force that choice early.

3. The chronic bottlenecks - constraint machines, key skills, critical tooling - not every station.

</details>

## Try this now

Plan [80, 160, 160] against capacity 100 and find the earliest period you must pre-build to stay feasible.

---
[← Cycle Counting Plan](cycle_counting.md) · [Back to MRP & Production Planning library](README.md) · [Drum-Buffer-Rope (DBR) →](drum_buffer_rope.md)
