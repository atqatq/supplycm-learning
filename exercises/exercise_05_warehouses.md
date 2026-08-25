---
title: "Warehouse Management Exercise | ABC Slotting Practice"
description: "Practice warehouse management: ABC analysis, slotting, and picking route planning."
keywords: "warehouse exercise, ABC slotting, order picking, warehouse layout practice"
---

# Exercise 5: Warehouses

## Problem

You manage a warehouse with 6 products. Monthly sales are:

| Product | Sales |
|---------|-------|
| Widget A | 1000 |
| Widget B | 800 |
| Widget C | 300 |
| Widget D | 150 |
| Widget E | 80 |
| Widget F | 20 |

### Tasks

1. Classify products using ABC analysis
2. Decide where to place each product in the warehouse
3. A customer orders Widget A, Widget C, and Widget E. Plan a picking route.

## Your Answer

(Write your work here)

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.inventory import abc_analysis
from supplycm.warehouse import warehouse_slotting_abc

products = [
    ('Widget A', 1000),
    ('Widget B', 800),
    ('Widget C', 300),
    ('Widget D', 150),
    ('Widget E', 80),
    ('Widget F', 20),
]

# 1. ABC analysis
result = abc_analysis(products)
for product, group, cum in result:
    print(f"{product}: Class {group}")

# 2. Slotting
items = [(p, s, 1) for p, s in products]
slotting = warehouse_slotting_abc(items, num_zones=3)
for item, zone in slotting:
    print(f"{item}: Zone {zone}")
```

### Expected Results

1. **ABC Classification**:
   - Widget A (1000) + Widget B (800) = 1800/2350 = 76.6% -> Class A
   - Widget A, B, C are likely A or B
   - Widget D, E, F are likely C

2. **Placement**:
   - Class A (Widget A, B): Zone 0 (closest to shipping door)
   - Class B (Widget C): Zone 1 (middle)
   - Class C (Widget D, E, F): Zone 2 (back of warehouse)

3. **Picking route**: Start at door, go to Widget A (Zone 0), then Widget C (Zone 1), then Widget E (Zone 2), return to door.

</details>
