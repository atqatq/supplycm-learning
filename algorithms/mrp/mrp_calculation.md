---
title: "MRP Calculation | supplycm Algorithm Library"
description: "Plain-English explanation of mrp_calculation from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, mrp_calculation, supply chain, plain english, mrp & production planning"
---

# MRP Calculation

> **Call it:** `from supplycm.mrp import mrp_calculation` · **Level:** Intermediate · **You need:** basic arithmetic only

The full MRP record for one item, period by period: gross requirements minus on hand and scheduled receipts leaves net requirements, which become planned receipts - shifted earlier by lead time into planned orders. Every ERP on earth runs this loop; now you can too, one item at a time.

**Think of it like this:** Your pantry planner: what the household will eat (gross), what you already have (on hand), what arrives soon (receipts) - the gap becomes this week's shopping list (orders).

## When to reach for it

- Understanding what your ERP actually does under the hood
- Testing lot sizes and safety stock settings before touching the system

## Try it with supplycm

```python
from supplycm.mrp import mrp_calculation

result = mrp_calculation(gross_requirements=[10, 20, 30, 40], scheduled_receipts=[0, 0, 0, 0], on_hand=5, lead_time=1, lot_size=50)
print(result)
```

You should see something like:

```text
{'net_requirements': [5, 0.0, 5, 0.0], 'planned_receipts': [50, 0.0, 50, 0.0], 'planned_orders': [0.0, 50.0, 0.0, 0.0], 'projected_on_hand': [45, 25, 45, 5]}
```

Four lists come back: watch net requirements trigger planned receipts, and lead time pull the planned orders one period earlier.

> **Watch out:** Change one parameter at a time (lot size, then safety stock) and watch which rows move - that is how MRP intuition is built.

## Check yourself

1. What are the four rows of an MRP record?
2. On hand 5, gross 10 - net requirement?
3. Why do planned orders release EARLIER than receipts?

<details>
<summary>Show answers</summary>

1. Gross requirements, scheduled receipts, projected on hand, and planned orders (with their releases).

2. 5 - MRP plans only the gap, never the gross.

3. Lead time offsetting - a receipt in week 4 with 1-week lead time must release in week 3.

</details>

## Try this now

Run it with safety_stock=10 as well and explain how every net requirement changes.

---
[← Backflush](backflush.md) · [Back to MRP & Production Planning library](README.md) · [Master Production Schedule (MPS) →](master_production_schedule.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
