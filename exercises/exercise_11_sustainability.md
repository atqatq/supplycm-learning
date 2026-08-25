---
title: "Sustainability Exercise | Carbon Footprint Calculation"
description: "Practice sustainable supply chain: calculate carbon footprint and compare transport modes."
keywords: "sustainability exercise, carbon footprint, green logistics, reverse logistics, environmental impact"
---

# Exercise 11: Sustainability

## Problem

You ship 500 packages per week. Each package:

- Travels 150 km by truck
- Weighs 3 kg

### Tasks

1. Calculate weekly CO2 emissions
2. If you switch to train (same distance), how much CO2 do you save?
3. If you reduce distance to 50 km (local sourcing), how much do you save with truck?

## Your Answer

```
Weekly CO2 (truck): ___ kg
Weekly CO2 (train): ___ kg
Savings (switch to train): ___ kg
Weekly CO2 (truck, 50km): ___ kg
Savings (local sourcing): ___ kg
```

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.sustainability import carbon_footprint_transport

# Total weight per week: 500 * 3 kg = 1500 kg = 1.5 tonnes
weight = 500 * 3 / 1000  # tonnes

# 1. Truck, 150 km
co2_truck = carbon_footprint_transport(150, weight, emission_factor=0.062)
print(f"Weekly CO2 (truck, 150km): {co2_truck:.1f} kg")

# 2. Train, 150 km
co2_train = carbon_footprint_transport(150, weight, emission_factor=0.022)
print(f"Weekly CO2 (train, 150km): {co2_train:.1f} kg")
print(f"Savings: {co2_truck - co2_train:.1f} kg")

# 3. Truck, 50 km
co2_local = carbon_footprint_transport(50, weight, emission_factor=0.062)
print(f"Weekly CO2 (truck, 50km): {co2_local:.1f} kg")
print(f"Savings: {co2_truck - co2_local:.1f} kg")
```

</details>
