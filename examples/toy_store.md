# Example: Online Toy Store

## The Business

You run an online toy store with 20 different products.

## Step 1: Forecast Demand

```python
from supplycm.forecasting import holt_winters

# 12 months of sales for a popular toy
sales = [100, 120, 90, 80, 70, 150, 200, 180, 90, 100, 250, 400]
level, trend, seasonal = holt_winters(sales, season_length=4)
print(f"Current level: {level[-1]:.0f}")
print(f"Trend: {trend[-1]:.0f}")
```

## Step 2: Inventory

```python
from supplycm.inventory import economic_order_quantity, abc_analysis

# ABC analysis of 20 toys
toys = [('Toy_' + str(i), 10000 - i * 400) for i in range(20)]
abc = abc_analysis(toys)
a_items = [t for t, c, _ in abc if c == 'A']
print(f"Class A items (watch closely): {len(a_items)}")

# EOQ for a Class A item
eoq = economic_order_quantity(5000, 50, 3)
print(f"Order {eoq:.0f} units of top toy each time")
```

## Step 3: Suppliers

```python
from supplycm.supplier import supplier_segmentation

suppliers = [
    ('Plastic Supplier', 0.8, 0.3),  # high profit, low risk
    ('Electronics Supplier', 0.9, 0.8),  # high profit, high risk
    ('Packaging Supplier', 0.2, 0.2),  # low profit, low risk
]
result = supplier_segmentation(suppliers)
for name, group in result:
    print(f"{name}: {group}")
```

## Step 4: Warehouse

```python
from supplycm.warehouse import warehouse_slotting_abc

# Slot toys by popularity
items = [(f'Toy_{i}', 1000 - i * 40, 1) for i in range(20)]
slotting = warehouse_slotting_abc(items, num_zones=3)
print(f"Top sellers in zone 0 (closest to door)")
```

## Step 5: Transportation (Delivery)

```python
from supplycm.routing import vrp_capacitated_greedy

# 10 customer deliveries, 2 trucks with capacity 50
demands = [0, 10, 15, 8, 12, 20, 5, 18, 10, 12]
distances = [[abs(i-j)*5 for j in range(10)] for i in range(10)]
routes = vrp_capacitated_greedy(distances, demands, 50)
print(f"Number of routes: {len(routes)}")
```

## Step 6: Quality

```python
from supplycm.quality import dpmo

# 2000 toys shipped, 3 things could go wrong, 15 defects
dpmo_value = dpmo(15, 2000, 3)
print(f"DPMO: {dpmo_value}")
```

## Step 7: Lean

```python
from supplycm.lean import takt_time, oee

# Pack 100 orders per day, 8 hours available
takt = takt_time(480, 100)
print(f"Pack one order every {takt:.1f} minutes")

# Packing station efficiency
oee_value = oee(0.88, 0.92, 0.99)
print(f"Packing OEE: {oee_value*100:.1f}%")
```

## Summary

An online toy store needs to:
- Forecast seasonal demand (toys sell more in holidays)
- Manage 20+ products with ABC analysis
- Work with multiple suppliers
- Organize warehouse for fast picking
- Plan delivery routes
- Maintain quality
- Pack orders efficiently
