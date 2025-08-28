---
title: "Demand Time Fence | supplycm Algorithm Library"
description: "Plain-English explanation of demand_time_fence from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, demand_time_fence, supply chain, plain english, mrp & production planning"
---

# Demand Time Fence

> **Call it:** `from supplycm.mrp import demand_time_fence` · **Level:** Intermediate · **You need:** basic arithmetic only

Inside the demand time fence, planning freezes: only real customer orders count, not forecast changes - the factory is already committed. Outside the fence, forecasts move freely. The fence protects stability in the near term while keeping flexibility further out.

**Think of it like this:** A restaurant kitchen: tonight's tickets are locked; next week's menu can still change freely.

## When to reach for it

- Protecting near-term production schedules from forecast churn
- Teaching sales why 'small' changes inside the fence cost real money

## Try it with supplycm

```python
from supplycm.mrp import demand_time_fence

result = demand_time_fence(gross_requirements=[100, 100, 100, 100], actual_orders=[50, 60, 0, 0], fence_period=2)
print(result)
```

You should see something like:

```text
[50, 60, 100, 100]
```

Periods 1-2 show actual orders (50, 60); periods 3-4 show forecast (100) - the fence switches the planning source at period 3.

## Check yourself

1. What counts as demand INSIDE the fence?
2. Sales insists on adding 20 units inside the fence. Who approves?
3. Where should the fence sit?

<details>
<summary>Show answers</summary>

1. Actual customer orders only - forecasts are ignored because production is already committed.

2. An escalation - it disrupts committed supply; someone senior trades off cost and customer impact.

3. Roughly at the cumulative lead time - changes before that point are physically hard to honor.

</details>

## Try this now

Set fence_period=1 vs 3 on the same data and describe how the planning source shifts.

---
[← Capacity Requirements Planning (CRP)](capacity_requirements_planning.md) · [Back to MRP & Production Planning library](README.md) · [Planning Time Fence →](planning_time_fence.md)
