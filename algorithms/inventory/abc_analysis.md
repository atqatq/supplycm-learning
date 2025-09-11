---
title: "ABC Analysis | supplycm Algorithm Library"
description: "Plain-English explanation of abc_analysis from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, abc_analysis, supply chain, plain english, inventory"
---

# ABC Analysis

> **Call it:** `from supplycm.inventory import abc_analysis` · **Level:** Beginner · **You need:** basic arithmetic only

ABC sorts SKUs by the value they move: A items are the vital few (about 20% of items, 80% of value), B the middle, C the trivial many. It converts 'we have 5,000 SKUs' into 'focus here first' - the oldest and best triage in inventory management.

**Think of it like this:** Sorting your closet: a few outfits you wear constantly (A), many you barely touch (C) - manage attention accordingly.

## When to reach for it

- Deciding which items get tight control and frequent counts
- Prioritizing cycle counting, forecasting effort, and slot placement

## Try it with supplycm

```python
from supplycm.inventory import abc_analysis

result = abc_analysis(items=[('laptop', 60000.0), ('mouse', 8000.0), ('cable', 2000.0), ('sticker', 500.0), ('bag', 9000.0)])
print(result)
```

You should see something like:

```text
[['laptop', 'A', 0.7547], ['bag', 'B', 0.8679], ['mouse', 'C', 0.9686], ['cable', 'C', 0.9937], ['sticker', 'C', 1.0]]
```

Each item gets its class - the laptop dominates value and lands in A; stickers fall to C no matter how cute they are.

> **Watch out:** Pareto in action: a minority of SKUs carries most of the value - manage them like it.

## Check yourself

1. What are typical A/B/C cutoffs?
2. A C-class item is the ONLY part keeping the line running. What now?
3. How often should ABC classes be refreshed?

<details>
<summary>Show answers</summary>

1. About 80% of cumulative value for A, 95% for B - the exact numbers matter less than the discipline.

2. Value-based ABC misses criticality - that's why criticality overlays (like VED for spares) exist.

3. At least annually - products drift between classes as the business changes.

</details>

## Try this now

ABC-classify 10 items you invent; then decide which 3 deserve weekly attention and which get a yearly glance.

---
[← Stockout Cost](stockout_cost.md) · [Back to Inventory library](README.md) · [XYZ Analysis →](xyz_analysis.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
