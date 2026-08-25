---
title: "Inventory Management Exercise | EOQ Practice"
description: "Practice inventory management: calculate EOQ, safety stock, and reorder point with this exercise."
keywords: "inventory exercise, EOQ practice, safety stock, reorder point, inventory management problems"
---

# Exercise 3: Inventory

## Problem

You run a t-shirt shop. Here is your data:

- Annual demand: 5000 t-shirts
- Ordering cost: $30 per order
- Holding cost: $4 per shirt per year
- Lead time: 2 weeks
- Demand standard deviation: 15 shirts per week
- You want 95% service level (Z = 1.645)

### Tasks

1. Calculate the EOQ
2. Calculate safety stock
3. Calculate the reorder point
4. How many orders will you place per year?

## Your Answer

```
EOQ: ___

Safety stock: ___

Reorder point: ___

Orders per year: ___
```

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.inventory import economic_order_quantity, safety_stock_normal, reorder_point

eoq = economic_order_quantity(5000, 30, 4)
ss = safety_stock_normal(1.645, 15, 2)
demand_per_week = 5000 / 52
rop = reorder_point(demand_per_week, 2, ss)

print(f"EOQ: {eoq:.0f} shirts")
print(f"Safety stock: {ss:.0f} shirts")
print(f"Reorder point: {rop:.0f} shirts")
print(f"Orders per year: {5000 / eoq:.1f}")
```

### Expected Results

1. EOQ = sqrt(2 * 5000 * 30 / 4) = sqrt(75000) = about 274 shirts
2. Safety stock = 1.645 * 15 * sqrt(2) = about 35 shirts
3. Reorder point = (96 * 2) + 35 = about 227 shirts
4. Orders per year = 5000 / 274 = about 18 orders

</details>
