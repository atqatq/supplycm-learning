---
title: "Least Period Cost Heuristic | supplycm Algorithm Library"
description: "Plain-English explanation of least_period_cost from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, least_period_cost, supply chain, plain english, inventory"
---

# Least Period Cost Heuristic

> **Call it:** `from supplycm.inventory import least_period_cost` · **Level:** Advanced · **You need:** basic arithmetic only

Another member of the family: extend the lot while the TOTAL cost per period covered keeps decreasing - a subtle variant on the same idea with its own stopping point. On most data it lands near its cousins; on yours, it might land better. Cheap to try, easy to compare.

**Think of it like this:** Three roommates with slightly different rules for splitting the heating bill - all reasonable, each occasionally fairest.

## When to reach for it

- Comparing multiple heuristics before standardizing on one
- Situations where you must justify the rule to auditors

## Try it with supplycm

```python
from supplycm.inventory import least_period_cost

result = least_period_cost(demands=[10, 20, 30, 40], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[0, 3], 160.0]
```

Its chosen lots and cost - line it up beside Silver-Meal and Least Unit Cost; agreement builds confidence, differences start discussions.

## Check yourself

1. Why do these heuristics disagree sometimes?
2. How do you pick ONE rule for your ERP?
3. What's the cost of heuristic imperfection?

<details>
<summary>Show answers</summary>

1. Different denominators (period, unit, period-covered) reward different demand shapes - none is universally best.

2. Backtest on your own demand history across items - choose by total cost and stability, not by textbook elegance.

3. Usually a few percent vs optimal - far less than the cost of stale parameters nobody reviews.

</details>

## Try this now

Run all three heuristics on the same 8-period demand and rank them by cost; note which you could explain best.

---
[← Least Unit Cost Heuristic](least_unit_cost.md) · [Back to Inventory library](README.md) · [Part-Period Balancing (PPB) →](part_period_balancing.md)
