---
title: "ABC-XYZ Demand Classification | supplycm Algorithm Library"
description: "Plain-English explanation of demand_class_abc_xyz from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, demand_class_abc_xyz, supply chain, plain english, demand planning"
---

# ABC-XYZ Demand Classification

> **Call it:** `from supplycm.demand import demand_class_abc_xyz` · **Level:** Intermediate · **You need:** basic arithmetic only

This combines two lenses: ABC (how much value a product drives) and XYZ (how predictable its demand is). Each product lands in a cell like AX (high value, steady - automate and watch closely) or CZ (low value, erratic - minimize effort and stock). The grid becomes your policy map.

**Think of it like this:** Sorting students by grades AND attendance: the top students with perfect attendance need a different plan than brilliant chaos agents.

## When to reach for it

- Designing inventory policies per class instead of one-size-fits-all
- Deciding where to spend planner time and where to automate

## Try it with supplycm

```python
from supplycm.demand import demand_class_abc_xyz

result = demand_class_abc_xyz(abc=[('SKU1', 'A'), ('SKU2', 'C')], xyz=[('SKU1', 'X'), ('SKU2', 'Z')])
print(result)
```

You should see something like:

```text
[['SKU1', 'AX'], ['SKU2', 'CZ']]
```

SKU1 is AX - high value and predictable, deserving tight, automated control; SKU2 is CZ - cheap and chaotic, keep it simple and cheap to manage.

## Check yourself

1. What does the AX cell mean and how do you treat it?
2. What about CZ items?
3. Which cell is the most dangerous to ignore?

<details>
<summary>Show answers</summary>

1. High value, steady demand - automate replenishment with tight service targets.

2. Low value, erratic demand - simple rules, minimal stock, minimal planner time.

3. AZ - high value but erratic: it hurts the most when wrong and resists automation.

</details>

## Try this now

Classify 6 of your (real or invented) products into the 3x3 grid and write one policy line per occupied cell.

---
[← Demand Sensing](demand_sensing.md) · [Back to Demand Planning library](README.md) · [Trend + Seasonal Forecast →](trend_seasonal_decomposition_forecast.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
