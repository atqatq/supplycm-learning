---
title: "Safety Stock (Normal Demand) | supplycm Algorithm Library"
description: "Plain-English explanation of safety_stock_normal from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, safety_stock_normal, supply chain, plain english, inventory"
---

# Safety Stock (Normal Demand)

> **Call it:** `from supplycm.inventory import safety_stock_normal` · **Level:** Intermediate · **You need:** basic arithmetic only

Safety stock is the cushion against demand surprises during lead time. This version uses the classic normal-demand recipe: z-score (service level you want) x demand variability x square root of lead time. Want fewer stockouts? Raise z. Wilder demand? More cushion.

**Think of it like this:** Extra cash in your wallet beyond the planned spend - enough that a surprise taxi or coffee doesn't strand you.

## When to reach for it

- Steady products with roughly bell-shaped demand swings
- Translating a service-level promise into an actual stock number

## Try it with supplycm

```python
from supplycm.inventory import safety_stock_normal

result = safety_stock_normal(z_score=1.65, demand_std=12, lead_time=4)
print(result)
```

You should see something like:

```text
39.6
```

About 24 units - enough to cover demand swings at roughly a 95% chance of not stocking out per cycle.

## Check yourself

1. What does z = 1.65 mean here?
2. Lead time quadruples. Safety stock?
3. Demand std falls to near zero. Safety stock?

<details>
<summary>Show answers</summary>

1. About 95% cycle service level - in roughly 19 of 20 replenishment cycles, stock lasts.

2. Doubles - the square root law again: uncertainty grows slower than time.

3. Nearly zero - perfectly predictable demand needs no cushion at all.

</details>

## Try this now

Compute safety stock for 98% service (z about 2.05) vs 90% (z about 1.28) and price the difference in holding cost.

---
[← Reorder Point (ROP)](reorder_point.md) · [Back to Inventory library](README.md) · [Safety Stock with Lead Time Variability →](safety_stock_with_lead_time_var.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
