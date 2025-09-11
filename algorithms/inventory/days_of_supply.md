---
title: "Days of Supply | supplycm Algorithm Library"
description: "Plain-English explanation of days_of_supply from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, days_of_supply, supply chain, plain english, inventory"
---

# Days of Supply

> **Call it:** `from supplycm.inventory import days_of_supply` · **Level:** Beginner · **You need:** basic arithmetic only

How many days will current inventory last at the current consumption rate? Stock divided by daily demand. It is the fastest health check in inventory: two warehouses with equal units but different demand have very different futures.

**Think of it like this:** Fuel gauge in kilometers-remaining, not liters - range is what tells you whether to stop now.

## When to reach for it

- Daily operations reviews across many SKUs
- Comparing stock adequacy between locations with different volumes

## Try it with supplycm

```python
from supplycm.inventory import days_of_supply

result = days_of_supply(avg_inventory=900, annual_demand=7300, days_per_year=365)
print(result)
```

You should see something like:

```text
45.0
```

45 days of cover - comfortable for steady items, worrying for perishables, lazy for A-class fast movers.

## Check yourself

1. Why is days of supply fairer than raw units across sites?
2. What target days of supply fits an A item?
3. Perishables and days of supply - special care?

<details>
<summary>Show answers</summary>

1. It normalizes by demand pace - 900 units means abundance at 10/day and two weeks at 60/day.

2. Lower - fast movers turn quickly and errors self-correct; C items can afford more days.

3. Always compare against shelf life, not just demand - '40 days of stock' of a 21-day-shelf-life item is a write-off.

</details>

## Try this now

Compute days of supply for 3 SKUs with different demand rates and flag which one should trigger action today.

---
[← Inventory Position](inventory_position.md) · [Back to Inventory library](README.md) · [Inventory Turnover Ratio →](inventory_turnover_ratio.md)
