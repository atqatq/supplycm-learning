# Example: Bicycle Shop

## The Business

A bicycle shop that sells and services bikes.

## Key Decisions

### 1. Forecast

```python
from supplycm.forecasting import holt_winters

# Bikes sell more in spring/summer
sales = [20, 25, 40, 60, 70, 65, 50, 35, 25, 20, 15, 18]
level, trend, seasonal = holt_winters(sales, season_length=4)
print(f"Current level: {level[-1]:.0f}")
```

### 2. Inventory

```python
from supplycm.inventory import economic_order_quantity, reorder_point

eoq = economic_order_quantity(400, 80, 25)  # 400 bikes/year
ss = 10  # safety stock
rop = reorder_point(8, 2, ss)  # 8/week, 2 weeks lead time
print(f"Order {eoq:.0f} bikes, reorder at {rop}")
```

### 3. S&OP

```python
from supplycm.sop import production_chase_strategy

# Monthly demand (seasonal)
demand = [20, 25, 40, 60, 70, 65, 50, 35, 25, 20, 15, 18]
plan = production_chase_strategy(demand)
print(f"Order plan: {plan}")
```

### 4. Quality (Service Department)

```python
from supplycm.quality import dpmo

# 500 repairs, 3 things could go wrong, 5 complaints
dpmo_value = dpmo(5, 500, 3)
print(f"Service DPMO: {dpmo_value}")
```

## Key Insights

- Bicycles are seasonal (forecast with Holt-Winters)
- Order in batches (EOQ)
- Plan orders monthly (S&OP)
- Track service quality (DPMO)
