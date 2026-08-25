---
title: "EOQ Step by Step: How Economic Order Quantity Works"
description: "Detailed breakdown of EOQ formula with step-by-step calculation. Learn why ordering cost equals holding cost at EOQ."
keywords: "EOQ step by step, economic order quantity explained, EOQ calculation, inventory cost optimization"
---

# How EOQ Works Step by Step

## The Problem

You sell toys. Every time you order toys from the supplier, it costs $100. Every toy you keep in storage costs $5 per year. How many should you order at once?

## The Two Costs

### Cost 1: Ordering Cost

Every order costs money. The more often you order, the more you pay.

```python
# If you order 10 times per year:
ordering_cost_per_year = number_of_orders * cost_per_order
# = 10 * 100
# = $1000 per year
```

### Cost 2: Holding Cost

Every toy in storage costs money. The more you order at once, the more you hold.

```python
# If you order 1000 toys at a time:
average_inventory = order_quantity / 2
# = 1000 / 2
# = 500 toys (average throughout the year)

holding_cost_per_year = average_inventory * cost_per_unit_per_year
# = 500 * 5
# = $2500 per year
```

Why divide by 2? Because inventory goes from full (just ordered) to empty (right before next order). Average is half.

## The Total Cost

```python
total_cost = ordering_cost + holding_cost
```

## Finding the Best Number

We want the order quantity that gives the lowest total cost. The formula is:

```python
eoq = (2 * annual_demand * ordering_cost / holding_cost) ** 0.5
```

### Step by Step Example

```python
# Given:
annual_demand = 12000   # toys per year
ordering_cost = 100     # dollars per order
holding_cost = 5        # dollars per toy per year

# Step 1: Multiply 2 * demand * ordering_cost
step1 = 2 * 12000 * 100
print(f'Step 1: 2 * {annual_demand} * {ordering_cost} = {step1}')
# = 2,400,000

# Step 2: Divide by holding_cost
step2 = step1 / holding_cost
print(f'Step 2: {step1} / {holding_cost} = {step2}')
# = 480,000

# Step 3: Take square root (that is what ** 0.5 means)
eoq = step2 ** 0.5
print(f'Step 3: {step2} ** 0.5 = {eoq:.0f}')
# = 693

print(f'\nEOQ = {eoq:.0f} toys per order')
```

### Try it with supplycm

```python
from supplycm.inventory import economic_order_quantity

eoq = economic_order_quantity(12000, 100, 5)
print(f'EOQ: {eoq:.0f} toys')
```

## Check the Costs

```python
annual_demand = 12000
eoq = 693

# How many orders per year?
orders_per_year = annual_demand / eoq
# = 12000 / 693 = 17.3 orders

# Ordering cost
ordering_cost = orders_per_year * 100
# = 17.3 * 100 = $1,732

# Average inventory
avg_inventory = eoq / 2
# = 693 / 2 = 347 toys

# Holding cost
holding_cost = avg_inventory * 5
# = 347 * 5 = $1,732

# Total cost
total = ordering_cost + holding_cost
# = $3,464

print(f'Orders per year: {orders_per_year:.1f}')
print(f'Ordering cost: ${ordering_cost:,.0f}')
print(f'Holding cost: ${holding_cost:,.0f}')
print(f'Total cost: ${total:,.0f}')
```

Notice: ordering cost and holding cost are equal! That is what EOQ does. It finds the point where both costs are balanced.

## What Happens If You Order More?

```python
# What if you order 1000 instead of 693?
order_qty = 1000
orders = 12000 / order_qty  # 12 orders
order_cost = orders * 100   # $1,200
hold_cost = (order_qty / 2) * 5  # $2,500
total = order_cost + hold_cost   # $3,700

print(f'Order 1000: total cost = ${total}')
# $3,700 (higher than EOQ!)
```

## What Happens If You Order Less?

```python
# What if you order 400 instead of 693?
order_qty = 400
orders = 12000 / order_qty  # 30 orders
order_cost = orders * 100   # $3,000
hold_cost = (order_qty / 2) * 5  # $1,000
total = order_cost + hold_cost   # $4,000

print(f'Order 400: total cost = ${total}')
# $4,000 (even higher!)
```

## Conclusion

EOQ finds the sweet spot. Order more = too much holding cost. Order less = too much ordering cost. EOQ = just right.

## Key Takeaway

```python
eoq = (2 * annual_demand * ordering_cost / holding_cost) ** 0.5
```

- Order more often = high ordering cost
- Order bigger batches = high holding cost
- EOQ balances both to give lowest total cost
