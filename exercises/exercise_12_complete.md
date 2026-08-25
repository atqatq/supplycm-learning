---
title: "Complete Supply Chain Exercise | Coffee Shop Planning"
description: "Comprehensive exercise: plan an entire coffee shop supply chain from forecasting to sustainability."
keywords: "supply chain exercise, complete case study, coffee shop, integrated supply chain planning"
---

# Exercise 12: Complete Scenario

## Problem

You are opening a coffee shop. Plan your entire supply chain.

### Given Information

- You expect to sell 50 cups of coffee per day
- You are open 300 days per year
- Coffee beans cost $10 per pound
- Each cup uses 0.05 pounds of beans
- Ordering cost: $25 per order
- Holding cost: $2 per pound per year
- Lead time: 1 week
- Demand standard deviation: 5 pounds per week
- Supplier offers revenue sharing: $6 per pound + 10% of your revenue
- You sell coffee for $4 per cup

### Tasks

1. Calculate annual bean demand
2. Calculate EOQ for beans
3. Calculate safety stock (97.5% service level)
4. Calculate reorder point
5. Compare standard vs revenue sharing contract
6. Calculate weekly CO2 if beans travel 500 km by truck (weight in tonnes)
7. What is your takt time if you are open 8 hours?

## Your Answer

(Work through each task)

---

<details>
<summary>Click to reveal full solution</summary>

### Using supplycm

```python
from supplycm.forecasting import average_method
from supplycm.inventory import economic_order_quantity, safety_stock_normal, reorder_point
from supplycm.contracts import revenue_sharing_contract
from supplycm.sustainability import carbon_footprint_transport
from supplycm.lean import takt_time

# 1. Annual bean demand
cups_per_year = 50 * 300  # 15000 cups
beans_per_year = cups_per_year * 0.05  # 750 pounds
print(f"Annual bean demand: {beans_per_year} pounds")

# 2. EOQ
eoq = economic_order_quantity(750, 25, 2)
print(f"EOQ: {eoq:.0f} pounds per order")

# 3. Safety stock
ss = safety_stock_normal(1.96, 5, 1)
print(f"Safety stock: {ss:.0f} pounds")

# 4. Reorder point
weekly_demand = 750 / 52
rop = reorder_point(weekly_demand, 1, ss)
print(f"Reorder point: {rop:.0f} pounds")

# 5. Compare contracts
# Standard: buy at $10, sell at $4 per cup
standard_revenue = cups_per_year * 4
standard_cost = beans_per_year * 10
standard_profit = standard_revenue - standard_cost
print(f"Standard contract profit: ${standard_profit}")

# Revenue sharing: buy at $6, share 10% of revenue
rs = revenue_sharing_contract(6, 4, 0.10, cups_per_year, 10)
# Note: this calculates per-cup, adjust for scale
print(f"Revenue sharing: Supplier=${rs['supplier_profit']}, Retailer=${rs['retailer_profit']}")

# 6. Weekly CO2
weekly_beans = weekly_demand  # pounds
weekly_beans_tonnes = weekly_beans / 2204.62  # convert pounds to tonnes
co2 = carbon_footprint_transport(500, weekly_beans_tonnes)
print(f"Weekly CO2: {co2:.2f} kg")

# 7. Takt time
available_time = 8 * 60  # 480 minutes
daily_demand = 50
takt = takt_time(available_time, daily_demand)
print(f"Takt time: {takt} minutes per cup")
```

### Key Insights

- You need about 750 pounds of beans per year
- Order about 137 pounds each time (EOQ)
- Keep 10 pounds as safety stock
- Reorder when inventory drops to 24 pounds
- Revenue sharing might be better if it aligns incentives
- Weekly CO2 is small but adds up over the year
- You need to make one cup every 9.6 minutes

</details>
