---
title: "Inventory Management: EOQ, Safety Stock, Reorder Point"
description: "Learn inventory management: Economic Order Quantity (EOQ), safety stock, reorder point, ABC analysis, and newsvendor model. Python code examples included."
keywords: "inventory management, EOQ, economic order quantity, safety stock, reorder point, ABC analysis, newsvendor model, stock management"
---

# Module 3: Having the Right Amount of Stuff (Inventory)

## The Big Idea

Inventory is the stuff a business keeps in storage. Too much is wasteful. Too little means lost sales. The trick is finding the right amount.

## Why Does It Matter?

Picture a toy store before the holidays.

- Too few toys: customers leave, you lose money
- Too many toys: after the holidays, they sit in storage costing money

Every business has this problem. Good inventory management saves money and keeps customers happy.

## The Most Famous Formula: EOQ

EOQ stands for Economic Order Quantity. It tells you the best amount to order each time.

The formula balances two costs:

1. **Ordering cost**: Every time you place an order, it costs money (paperwork, delivery, etc.)
2. **Holding cost**: Keeping stuff in storage costs money (rent, insurance, spoilage)

If you order a lot at once, you pay less in ordering but more in holding. If you order a little at a time, you pay less in holding but more in ordering. EOQ finds the sweet spot.

### The Formula in Python Notation

```python
eoq = (2 * annual_demand * ordering_cost / holding_cost) ** 0.5
```

Where:
- `annual_demand` = how many you sell per year
- `ordering_cost` = cost per order
- `holding_cost` = cost to store one unit for one year

### Try it with supplycm

```python
from supplycm.inventory import economic_order_quantity

annual_demand = 12000   # toys per year
ordering_cost = 100     # dollars per order
holding_cost = 5        # dollars per unit per year

eoq = economic_order_quantity(annual_demand, ordering_cost, holding_cost)
print(f"Order {eoq:.0f} toys each time")
# Output: Order 693 toys each time
```

## Safety Stock: Your Just-In-Case Buffer

What if demand is higher than expected? What if the supplier is late?

Safety stock is extra inventory to protect you from surprises.

### The Formula in Python Notation

```python
import math
safety_stock = z_score * demand_std * (lead_time ** 0.5)
```

Where:
- `z_score` = service level (how sure you want to be). 1.96 means 97.5% sure
- `demand_std` = how much demand varies (standard deviation)
- `lead_time` = how long it takes to get new stock

### Try it with supplycm

```python
from supplycm.inventory import safety_stock_normal

demand_std = 30       # demand varies by 30 units per week
lead_time = 2         # supplier takes 2 weeks to deliver
z_score = 1.96        # 97.5% service level

safety = safety_stock_normal(z_score, demand_std, lead_time)
print(f"Keep {safety:.0f} units as safety stock")
```

## Reorder Point: When to Order More

The reorder point is the inventory level that tells you "time to order more."

### The Formula in Python Notation

```python
reorder_point = (demand_per_week * lead_time) + safety_stock
```

### Try it with supplycm

```python
from supplycm.inventory import reorder_point, safety_stock_normal

demand_per_week = 250  # you sell 250 per week
lead_time = 2          # supplier takes 2 weeks to deliver
safety = safety_stock_normal(1.96, 30, 2)

rop = reorder_point(demand_per_week, lead_time, safety)
print(f"When inventory drops to {rop:.0f}, place a new order")
```

## ABC Analysis: Not All Stuff Is Equal

Some products sell a lot. Some sell very little. You should manage them differently.

ABC analysis sorts products into three groups:

- **A items**: Top 20% of products, but they make up 80% of sales. Watch these closely.
- **B items**: Next 30% of products, 15% of sales. Manage normally.
- **C items**: Bottom 50% of products, only 5% of sales. Do not spend much time on these.

### Try it with supplycm

```python
from supplycm.inventory import abc_analysis

products = [
    ('Toy A', 50000),
    ('Toy B', 30000),
    ('Toy C', 10000),
    ('Toy D', 5000),
    ('Toy E', 3000),
    ('Toy F', 2000),
]

result = abc_analysis(products)
for product, group, cumulative in result:
    print(f"{product}: Class {group}")
```

## Quick Quiz

1. What does EOQ stand for?
2. Why do we need safety stock?
3. If `annual_demand = 1000`, `ordering_cost = 50`, and `holding_cost = 2`, what is `eoq`?
4. In ABC analysis, which class should you watch most closely?

<details>
<summary>Click to reveal answers</summary>

1. Economic Order Quantity
2. To protect against demand surprises and late deliveries
3. `eoq = (2 * 1000 * 50 / 2) ** 0.5` = `50000 ** 0.5` = about 224 units
4. Class A (top 20% of products make 80% of sales)

</details>

## Exercise

You run a cookie shop.

1. `annual_demand = 20000` cookies
2. `ordering_cost = 20` dollars per order
3. `holding_cost = 0.50` dollars per cookie per year
4. `demand_std = 50` cookies per week
5. `lead_time = 1` week

Calculate:
- The EOQ (how many cookies to order each time)
- The safety stock (for 97.5% service level)
- The reorder point (when to order more)

## Key Words

- **Inventory**: Stuff kept in storage
- **EOQ**: The best order quantity to minimize total cost
- **Safety stock**: Extra inventory for protection
- **Reorder point**: The inventory level that triggers a new order
- **ABC analysis**: Sorting products by importance

## What's Next?

Now you know how much to order. But who makes the stuff you order? The next lesson is about suppliers.

Next: [Module 4 - Working with Suppliers](04_suppliers.md)
