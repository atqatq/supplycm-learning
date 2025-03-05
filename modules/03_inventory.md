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

### The Formula

```
EOQ = square root of (2 x D x S / H)
```

Where:
- D = demand per year (how many you sell)
- S = ordering cost (per order)
- H = holding cost (per unit per year)

### Try it with supplycm

```python
from supplycm.inventory import economic_order_quantity

# You sell 12000 toys per year
# Each order costs $100 to place
# Each toy costs $5 per year to store

eoq = economic_order_quantity(demand=12000, ordering_cost=100, holding_cost=5)
print(f"Order {eoq:.0f} toys each time")
# Output: Order 693 toys each time
```

## Safety Stock: Your Just-In-Case Buffer

What if demand is higher than expected? What if the supplier is late?

Safety stock is extra inventory to protect you from surprises.

### The Formula

```
Safety Stock = Z x sigma x square root of L
```

Where:
- Z = service level (how sure you want to be). 1.96 means 97.5% sure
- sigma = how much demand varies (standard deviation)
- L = lead time (how long it takes to get new stock)

### Try it with supplycm

```python
from supplycm.inventory import safety_stock_normal

# Demand varies by 30 units per week
# Lead time is 2 weeks
# You want 97.5% service level (Z = 1.96)

ss = safety_stock_normal(z_score=1.96, demand_std=30, lead_time=2)
print(f"Keep {ss:.0f} units as safety stock")
```

## Reorder Point: When to Order More

The reorder point is the inventory level that tells you "time to order more."

### The Formula

```
Reorder Point = (demand per week x lead time in weeks) + safety stock
```

### Try it with supplycm

```python
from supplycm.inventory import reorder_point, safety_stock_normal

demand_per_week = 250  # you sell 250 per week
lead_time = 2  # supplier takes 2 weeks to deliver
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
3. If you sell 1000 units per year, ordering cost is $50, and holding cost is $2, what is the EOQ?
4. In ABC analysis, which class should you watch most closely?

<details>
<summary>Click to reveal answers</summary>

1. Economic Order Quantity
2. To protect against demand surprises and late deliveries
3. EOQ = square root of (2 x 1000 x 50 / 2) = square root of 50000 = about 224 units
4. Class A (top 20% of products make 80% of sales)

</details>

## Exercise

You run a cookie shop.

1. You sell 20000 cookies per year
2. Each order costs $20 to place
3. Each cookie costs $0.50 per year to store
4. Demand varies by 50 cookies per week
5. Your supplier takes 1 week to deliver

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
