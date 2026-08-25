---
title: "Bakery Operations: Supply Chain for Perishable Goods"
description: "Learn supply chain management for a bakery. Newsvendor model for perishable goods, quality control, and lean operations."
keywords: "bakery supply chain, perishable goods, newsvendor model, food supply chain, quality control, lean operations"
---

# Example: Bakery Operations

## The Business

A bakery making bread, cakes, and pastries.

## Key Decisions

### 1. Forecast Demand (perishable goods)

```python
from supplycm.forecasting import simple_moving_average

# Daily bread sales
sales = [200, 220, 210, 240, 260, 280, 250]
forecast = simple_moving_average(sales, window=3)
print(f"Tomorrow's forecast: {forecast[-1]:.0f} loaves")
```

### 2. Inventory (perishable - use newsvendor model)

```python
from supplycm.inventory import newsvendor_model
from math import erf, sqrt

# Bread cost $1, sells $3, salvage $0.50
# Demand averages 250 with std dev 30
def cdf(x):
    return 0.5 * (1 + erf((x - 250) / sqrt(2) / 30))

q = newsvendor_model(1, 3, 0.50, cdf)
print(f"Bake {q:.0f} loaves")
```

### 3. Quality

```python
from supplycm.quality import process_capability_cpk

# Bread weight spec: 500g +/- 20g
cpk = process_capability_cpk(520, 480, 502, 5)
print(f"Cpk: {cpk:.2f}")
```

### 4. Lean

```python
from supplycm.lean import cycle_time_efficiency

# Bread takes 4 hours (rising + baking), but 30 min is work
eff = cycle_time_efficiency(0.5, 4)
print(f"Efficiency: {eff*100:.0f}%")
```

## Key Insights

- Bakery products are perishable (newsvendor model is perfect)
- Must forecast daily (cannot stockpile)
- Quality matters (weight, taste, freshness)
- Most time is waiting (rising), not working
