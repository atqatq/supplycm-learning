---
title: "Least Unit Cost Heuristic | supplycm Algorithm Library"
description: "Plain-English explanation of least_unit_cost from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, least_unit_cost, supply chain, plain english, inventory"
---

# Least Unit Cost Heuristic

> **Call it:** `from supplycm.inventory import least_unit_cost` · **Level:** Advanced · **You need:** basic arithmetic only

A sibling heuristic with a different scoreboard: extend the order while the average cost PER UNIT keeps falling, not per period. Big-demand periods therefore attract longer lots. Simple to compute, easy to audit, robust to lumpy demand.

**Think of it like this:** Filling a group pizza order: keep adding slices while the price per slice drops - the pizza size follows the crowd, not the clock.

## When to reach for it

- Lumpy demands where per-period rules wobble
- Explaining lot sizing with per-unit intuition to non-analysts

## Try it with supplycm

```python
from supplycm.inventory import least_unit_cost

result = least_unit_cost(demands=[10, 20, 30, 40], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[0, 3], 160.0]
```

Order periods and cost come back - compare with Silver-Meal on the same data to see how the scoreboard changes the shape of lots.

## Check yourself

1. How does the per-unit view differ from Silver-Meal's per-period view?
2. Which heuristic handles one huge demand spike better?
3. Neither is optimal. Why use them?

<details>
<summary>Show answers</summary>

1. Per-unit divides by DEMAND covered, not periods - heavy periods can extend a lot without raising the average.

2. Often Least Unit Cost - the big period's demand dilutes holding quickly.

3. Speed, transparency, and near-optimality - perfect optimality (Wagner-Whitin) costs complexity that rarely pays back.

</details>

## Try this now

Run both heuristics on [50, 5, 5, 5] and explain why their first orders differ.

---
[← Silver-Meal Heuristic](silver_meal.md) · [Back to Inventory library](README.md) · [Least Period Cost Heuristic →](least_period_cost.md)
