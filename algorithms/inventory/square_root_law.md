---
title: "Square Root Law of Inventory | supplycm Algorithm Library"
description: "Plain-English explanation of square_root_law from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, square_root_law, supply chain, plain english, inventory"
---

# Square Root Law of Inventory

> **Call it:** `from supplycm.inventory import square_root_law` · **Level:** Intermediate · **You need:** basic arithmetic only

Centralize inventory into fewer locations and total safety stock falls with the square ROOT of the location count - halving variability across 4 sites needs only 2x one site's stock, not 4x. This computes the stock change when locations change. Consolidation math at its most elegant.

**Think of it like this:** Four people each carrying a spare umbrella vs two people sharing the risk - shared spares cover bad luck with fewer total umbrellas.

## When to reach for it

- Sizing the inventory impact of network consolidation
- Arguing for (or against) merging warehouses

## Try it with supplycm

```python
from supplycm.inventory import square_root_law

result = square_root_law(num_locations_before=4, num_locations_after=1, current_safety_stock=400)
print(result)
```

You should see something like:

```text
200.0
```

Total stock falls to 200 - one quarter of four sites' stock covers the pooled risk; run it backwards for de-consolidation shocks.

## Check yourself

1. Why does pooling need only the square root, not the full multiple?
2. You split one DC into 4 regional ones. Stock consequence?
3. What assumption makes this law honest?

<details>
<summary>Show answers</summary>

1. Independent site variations cancel when pooled - combined uncertainty grows slower than the count of sites.

2. Safety stock roughly doubles - the same law, now working against you.

3. Independence - if regions boom and bust together (correlated demand), pooling saves less than promised.

</details>

## Try this now

Compute the stock impact of going from 9 sites to 3 with 900 units of total safety stock - and explain it to a CFO in one sentence.

---
[← Weighted Average Cost](weighted_average_cost.md) · [Back to Inventory library](README.md) · [Risk Pooling Effect →](risk_pooling.md)
