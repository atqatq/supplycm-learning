---
title: "Part-Period Balancing (PPB) | supplycm Algorithm Library"
description: "Plain-English explanation of part_period_balancing from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, part_period_balancing, supply chain, plain english, inventory"
---

# Part-Period Balancing (PPB)

> **Call it:** `from supplycm.inventory import part_period_balancing` · **Level:** Advanced · **You need:** basic arithmetic only

PPB speaks one currency: the part-period (one unit held for one period). It extends an order while the accumulated part-periods cost less than one setup would - a stopping rule you can compute on a napkin. It is the intuition pump for all lot sizing.

**Think of it like this:** Deciding how many errands to chain into one trip: each extra stop adds waiting cost; you keep chaining until waiting would cost a whole new trip.

## When to reach for it

- Hand-computable lot sizing for teaching and audits
- Quick checks on system-generated lots

## Try it with supplycm

```python
from supplycm.inventory import part_period_balancing

result = part_period_balancing(demands=[10, 20, 30, 40], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[0, 3], 160.0]
```

Lots and cost come back - trace how cumulative part-periods creep toward the setup cost and trigger the stop exactly there.

## Check yourself

1. What is a part-period, in plain words?
2. How is the EPP threshold computed?
3. PPB vs Silver-Meal - why might they stop at different points?

<details>
<summary>Show answers</summary>

1. One unit waiting one period - the atom of holding cost that makes setups comparable.

2. Setup cost divided by holding cost per part-period - how many waiting-units one setup can 'afford'.

3. PPB watches absolute holding vs setup; Silver-Meal watches averages - the stop conditions genuinely differ.

</details>

## Try this now

Compute the EPP for setup 120, holding 1.5; verify by hand that PPB stops once part-periods cross it.

---
[← Least Period Cost Heuristic](least_period_cost.md) · [Back to Inventory library](README.md) · [Periodic Order Quantity (POQ) →](periodic_order_quantity.md)
