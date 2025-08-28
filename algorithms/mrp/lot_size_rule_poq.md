---
title: "Period Order Quantity (POQ) | supplycm Algorithm Library"
description: "Plain-English explanation of lot_size_rule_poq from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, lot_size_rule_poq, supply chain, plain english, mrp & production planning"
---

# Period Order Quantity (POQ)

> **Call it:** `from supplycm.mrp import lot_size_rule_poq` · **Level:** Intermediate · **You need:** basic arithmetic only

POQ orders several periods of demand at once - 'order every 3 weeks' instead of every week. It cuts the number of setups by grouping needs, while staying demand-driven (unlike a fixed quantity). Pick the period count, and POQ bundles accordingly.

**Think of it like this:** Doing one big grocery run every two weeks instead of daily top-ups - fewer trips, a fuller pantry.

## When to reach for it

- Moderate setup costs where L4L orders too often
- Demand that is reasonably steady period to period

## Try it with supplycm

```python
from supplycm.mrp import lot_size_rule_poq

result = lot_size_rule_poq(net_requirements=[10, 20, 30, 40], period=2)
print(result)
```

You should see something like:

```text
[30, 0.0, 70, 0.0]
```

Orders bundle two periods each: 30 then 70 - half the setups of L4L, at the cost of some holding.

## Check yourself

1. How does POQ choose quantities?
2. POQ period 1 equals which rule?
3. Longer POQ period: what rises and what falls?

<details>
<summary>Show answers</summary>

1. It sums the net requirements across the chosen number of periods whenever an order is placed.

2. Lot-for-lot - one period per order.

3. Holding cost rises; setup count (and cost) falls - the balance is the whole game.

</details>

## Try this now

For [15, 5, 25, 10, 20] compare setup count and average inventory for POQ period 1 vs 3.

---
[← Fixed Order Quantity (FOQ)](lot_size_rule_foq.md) · [Back to MRP & Production Planning library](README.md) · [Economic Part Period (EPP) Lot Sizing →](lot_size_rule_epr.md)
