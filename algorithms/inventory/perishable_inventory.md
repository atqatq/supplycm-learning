---
title: "Perishable Inventory Order | supplycm Algorithm Library"
description: "Plain-English explanation of perishable_inventory from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, perishable_inventory, supply chain, plain english, inventory"
---

# Perishable Inventory Order

> **Call it:** `from supplycm.inventory import perishable_inventory` · **Level:** Advanced · **You need:** basic arithmetic only

The newsvendor, tuned for goods that EXPIRE: bakery items, vaccines, fresh food. It weighs overage (unsold stock wasted), underage (missed sales), AND a shortage penalty, then returns the order quantity that balances all three. Perishables tolerate no lazy averages - every unit either sells or dies.

**Think of it like this:** A sushi chef's evening prep: too little and customers leave hungry; too much and fish is thrown out at close - the art, made arithmetic.

## When to reach for it

- Fresh food, flowers, media with sell-by dates, event stock
- Any product where leftover units have sharply reduced value

## Try it with supplycm

```python
from supplycm.inventory import perishable_inventory

result = perishable_inventory(unit_cost=5, selling_price=12, salvage_value=1, shortage_cost=3, demand_cdf=lambda q: min(max(q/150, 0), 1))
print(result)
```

You should see something like:

```text
107.1429
```

An optimal buy near the demand midpoint-plus - the shortage penalty nudges the order above where pure overage/underage math would sit.

## Check yourself

1. How does the shortage penalty change the order?
2. Salvage value rises (day-old bread sells). Order more or less?
3. Why can't you just order average demand?

<details>
<summary>Show answers</summary>

1. It raises the optimum - stockouts now cost goodwill on top of lost margin, so the model errs toward having stock.

2. More - overage shrinks, so bigger buys hurt less.

3. Because average ignores the asymmetry: leftover cost and missed-sale cost differ, and the difference moves the optimum off the mean.

</details>

## Try this now

Recompute with salvage_value=0 and shortage_cost=10; explain the swing in one sentence each.

---
[← Optimal Stockout Probability](optimal_stockout_probability.md) · [Back to Inventory library](README.md) · [Lot-for-Lot (L4L) →](lot_for_lot.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
