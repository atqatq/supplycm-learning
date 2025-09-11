---
title: "Demand During Lead Time | supplycm Algorithm Library"
description: "Plain-English explanation of demand_during_lead_time from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, demand_during_lead_time, supply chain, plain english, inventory"
---

# Demand During Lead Time

> **Call it:** `from supplycm.inventory import demand_during_lead_time` · **Level:** Beginner · **You need:** basic arithmetic only

The simplest building block in inventory: how much you expect to sell while waiting for replenishment - demand rate times lead time. Every reorder point starts with this number; get it wrong and everything downstream is wrong.

**Think of it like this:** How much food you eat during the week your grocery order is in transit - that is what your fridge must hold when you order.

## When to reach for it

- Manual reorder point setting without fancy formulas
- Sanity-checking what the ERP is assuming

## Try it with supplycm

```python
from supplycm.inventory import demand_during_lead_time

result = demand_during_lead_time(demand_rate=25, lead_time=8)
print(result)
```

You should see something like:

```text
200
```

200 units - the expected sales during the 8-day wait; the reorder point starts here and adds safety stock.

## Check yourself

1. Units mismatch alert: demand per DAY, lead time in WEEKS. What now?
2. Demand during lead time is 200 and you order at 200 with no safety stock. Risk?
3. Seasonal product: one ROP all year?

<details>
<summary>Show answers</summary>

1. Convert first - 25/day is 175/week; mixing units silently breaks every downstream number.

2. Any demand bump or delivery delay during the window means a stockout - that's why safety stock exists.

3. No - the lead-time demand part should follow the season too.

</details>

## Try this now

Compute lead-time demand for 120/week demand and 2.5-week lead time; add 1 week of safety stock and compare the two numbers.

---
[← Safety Stock with Lead Time Variability](safety_stock_with_lead_time_var.md) · [Back to Inventory library](README.md) · [Cycle Service Level from Safety Stock →](cycle_service_level.md)
