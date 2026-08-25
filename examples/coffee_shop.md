---
title: "Coffee Shop Supply Chain Example | Real Case Study"
description: "Complete supply chain analysis of a coffee shop. Forecast demand, calculate inventory, choose suppliers, and plan deliveries with Python code."
keywords: "coffee shop supply chain, supply chain example, case study, demand forecasting, inventory management, supplier selection"
---

# Example: Coffee Shop Supply Chain

## The Business

You run a coffee shop that sells 50 cups per day, 300 days per year.

## Step 1: Forecast Demand

```python
from supplycm.forecasting import single_exponential_smoothing

# Last 8 weeks of daily sales
daily_sales = [45, 48, 52, 50, 47, 55, 58, 53]
forecast = single_exponential_smoothing(daily_sales, alpha=0.3)
print(f"Expected sales tomorrow: {forecast[-1]:.0f} cups")
```

## Step 2: Inventory

Each cup uses 0.05 pounds of beans. Annual bean demand = 50 * 300 * 0.05 = 750 pounds.

```python
from supplycm.inventory import economic_order_quantity, safety_stock_normal, reorder_point

eoq = economic_order_quantity(750, 25, 2)  # 750 lbs/year, $25/order, $2/lb/year
ss = safety_stock_normal(1.96, 5, 1)  # Z=1.96, sigma=5, lead_time=1 week
rop = reorder_point(750/52, 1, ss)

print(f"Order {eoq:.0f} pounds each time")
print(f"Keep {ss:.0f} pounds as safety stock")
print(f"Reorder when down to {rop:.0f} pounds")
```

## Step 3: Supplier

Compare 3 bean suppliers using TOPSIS.

```python
from supplycm.supplier import topsis

# Score each supplier on Price, Quality, Delivery
decision_matrix = [
    [70, 90, 85],  # Supplier A
    [85, 75, 80],  # Supplier B
    [80, 85, 90],  # Supplier C
]

ranking = topsis(decision_matrix, [0.4, 0.35, 0.25],
                ['benefit', 'benefit', 'benefit'])
print(f"Best supplier: Supplier {ranking[0] + 1}")
```

## Step 4: Warehouse (Storage)

Store beans, cups, lids, milk, syrups.

```python
from supplycm.inventory import abc_analysis

items = [
    ('Coffee Beans', 7500),  # $10/lb * 750 lbs
    ('Milk', 3600),          # $2/gal * 1800 gallons
    ('Cups', 1500),
    ('Lids', 300),
    ('Syrups', 1200),
]

abc = abc_analysis(items)
for item, group, _ in abc:
    print(f"{item}: Class {group}")
```

## Step 5: Transportation

Beans are delivered from a roaster 50 km away.

```python
from supplycm.routing import tsp_nearest_neighbor

# If you have multiple deliveries (beans, milk, pastries)
distances = [
    [0,  50, 30, 20],  # from shop
    [50, 0,  60, 40],  # from roaster
    [30, 60, 0,  25],  # from dairy
    [20, 40, 25, 0],   # from bakery
]

route, total = tsp_nearest_neighbor(distances)
print(f"Delivery route: {route}")
print(f"Total distance: {total} km")
```

## Step 6: Quality

Check coffee quality (temperature, taste, consistency).

```python
from supplycm.quality import dpmo, sigma_level

# 5000 cups, 5 quality checks each, 20 defects found
dpmo_value = dpmo(20, 5000, 5)
sigma = sigma_level(dpmo_value)
print(f"DPMO: {dpmo_value}")
print(f"Sigma level: {sigma}")
```

## Step 7: Lean

How efficient is your coffee-making process?

```python
from supplycm.lean import takt_time, oee

# Open 8 hours = 480 min, demand 50 cups/day
takt = takt_time(480, 50)
print(f"Takt time: {takt:.1f} minutes per cup")

# Espresso machine: 90% available, 95% performance, 98% quality
oee_value = oee(0.90, 0.95, 0.98)
print(f"OEE: {oee_value*100:.1f}%")
```

## Step 8: S&OP

Plan monthly bean orders.

```python
from supplycm.sop import production_level_strategy

# Expected monthly demand (pounds)
demand = [60, 65, 70, 75, 65, 60, 55, 60, 65, 70, 75, 80]
plan = production_level_strategy(demand)
print(f"Order {plan[0]:.0f} pounds each month (level strategy)")
```

## Step 9: Contract

Sign a bean supply contract.

```python
from supplycm.contracts import revenue_sharing_contract

# Standard: buy at $10/lb
# Revenue sharing: buy at $7/lb, share 10% of cup sales
rs = revenue_sharing_contract(
    wholesale_price=7,
    retail_price=4,  # per cup
    revenue_share_fraction=0.10,
    demand=15000,  # cups per year
    unit_cost=5    # roaster's cost
)
print(f"Supplier profit: ${rs['supplier_profit']}")
print(f"Your profit: ${rs['retailer_profit']}")
```

## Step 10: Sustainability

Calculate CO2 from bean delivery.

```python
from supplycm.sustainability import carbon_footprint_transport

# 750 pounds = 0.34 tonnes, delivered 50 km by truck
co2 = carbon_footprint_transport(50, 0.34, 0.062)
print(f"Annual delivery CO2: {co2:.1f} kg")
```

## Summary

Running a coffee shop involves:
- Forecasting how many cups you will sell
- Ordering the right amount of beans (not too much, not too little)
- Choosing good suppliers
- Storing ingredients efficiently
- Delivering to customers (if you offer delivery)
- Maintaining coffee quality
- Working efficiently (lean)
- Planning monthly
- Making fair deals with suppliers
- Reducing environmental impact
