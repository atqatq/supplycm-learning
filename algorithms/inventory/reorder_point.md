---
title: "Reorder Point (ROP) | supplycm Algorithm Library"
description: "Plain-English explanation of reorder_point from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, reorder_point, supply chain, plain english, inventory"
---

# Reorder Point (ROP)

> **Call it:** `from supplycm.inventory import reorder_point` · **Level:** Beginner · **You need:** basic arithmetic only

The reorder point is the inventory level that says ORDER NOW. It covers what you expect to sell during the lead time, plus safety stock for surprises. Fall to ROP, place the order - inventory should just touch zero as the new stock lands.

**Think of it like this:** Refilling the car's fuel: the warning light comes on with enough range to reach the next station - that threshold is your ROP.

## When to reach for it

- Setting the trigger level in any continuous-review inventory system
- Auditing whether current trigger points match real lead times

## Try it with supplycm

```python
from supplycm.inventory import reorder_point

result = reorder_point(demand_rate=10, lead_time=6, safety_stock=15)
print(result)
```

You should see something like:

```text
75
```

75 units - sell 10 a day for the 6-day wait (60) plus a 15-unit cushion for the unexpected.

## Check yourself

1. What are the two ingredients of ROP?
2. Lead time doubles. What happens to ROP?
3. Safety stock of zero - when is that brave but OK?

<details>
<summary>Show answers</summary>

1. Expected demand during lead time (rate x time) plus safety stock.

2. The demand-during-lead-time part doubles - you cross the trigger much earlier.

3. When demand and supply are highly predictable and stockouts cost little - e.g., continuous production feeding.

</details>

## Try this now

Set ROP for daily demand 40, 9-day lead time, safety stock 50; then state what happens in a 12-day delay.

---
[← EOQ with Quantity Discounts](eoq_quantity_discount.md) · [Back to Inventory library](README.md) · [Safety Stock (Normal Demand) →](safety_stock_normal.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
