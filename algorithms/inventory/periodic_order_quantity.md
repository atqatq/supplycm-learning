---
title: "Periodic Order Quantity (POQ) | supplycm Algorithm Library"
description: "Plain-English explanation of periodic_order_quantity from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, periodic_order_quantity, supply chain, plain english, inventory"
---

# Periodic Order Quantity (POQ)

> **Call it:** `from supplycm.inventory import periodic_order_quantity` · **Level:** Advanced · **You need:** basic arithmetic only

POQ asks EOQ to pick a RHYTHM: convert the economic order quantity into an order-every-T-periods cadence, then bundle T periods of demand each time. The result is L4L's accuracy with fewer setups - a calendar-friendly compromise.

**Think of it like this:** Shopping every two weeks because that's what the EOQ math justifies - the list flexes each trip, the calendar stays fixed.

## When to reach for it

- Aligned with supplier delivery schedules (weekly, biweekly)
- Stabilizing purchasing workload across the month

## Try it with supplycm

```python
from supplycm.inventory import periodic_order_quantity

result = periodic_order_quantity(demands=[10, 20, 30, 40], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[0, 3], 280.0]
```

Its bundled orders and cost - compare with Silver-Meal: the cadence is fixed here, which sometimes costs a little, sometimes wins.

## Check yourself

1. How does POQ get its period count T?
2. POQ vs fixed order quantity - which is more flexible?
3. When does POQ waste money?

<details>
<summary>Show answers</summary>

1. From EOQ: T is roughly EOQ divided by average demand per period.

2. POQ flexes QUANTITY to demand; FOQ flexes TIMING. Pick based on whether your calendar or your batch size is the constraint.

3. Highly lumpy demand - bundling by calendar carries quiet periods' stock pointlessly; heuristics that read demand do better.

</details>

## Try this now

Compute T for EOQ 60 on average demand 20; then hand-build the POQ lots for the example and compare.

---
[← Part-Period Balancing (PPB)](part_period_balancing.md) · [Back to Inventory library](README.md) · [Wagner-Whitin (Optimal Lot Sizing) →](wagner_whitin.md)
