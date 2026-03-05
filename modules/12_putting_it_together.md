# Module 12: Putting It All Together

## The Big Idea

You have learned about the pieces of a supply chain. Now let us see how they fit together in a real scenario.

## A Complete Example: The Bicycle Shop

Imagine you run a bicycle shop. Let us walk through every decision you need to make.

### Step 1: Forecast Demand (Module 2)

How many bicycles will you sell next month?

```python
from supplycm.forecasting import single_exponential_smoothing

# Past 6 months of sales
sales = [120, 135, 130, 145, 140, 155]
forecast = single_exponential_smoothing(sales, alpha=0.3)
print(f"Expected sales next month: {forecast[-1]:.0f}")
```

### Step 2: Manage Inventory (Module 3)

How many bicycles should you order? When should you order?

```python
from supplycm.inventory import economic_order_quantity, safety_stock_normal, reorder_point

annual_demand = 1700  # about 142 per month
ordering_cost = 80    # cost per order
holding_cost = 25     # cost per bike per year

eoq = economic_order_quantity(annual_demand, ordering_cost, holding_cost)
ss = safety_stock_normal(1.96, 20, 2)  # Z=1.96, sigma=20, lead_time=2 weeks
rop = reorder_point(35, 2, ss)  # 35 per week, 2 weeks lead time

print(f"Order {eoq:.0f} bikes each time")
print(f"Keep {ss:.0f} bikes as safety stock")
print(f"Order more when inventory hits {rop:.0f}")
```

### Step 3: Choose Suppliers (Module 4)

Which supplier should you buy from?

```python
from supplycm.supplier import ahp_supplier_selection, topsis

# 3 criteria: Price, Quality, Delivery
weights = ahp_supplier_selection([
    [1, 3, 5],
    [1/3, 1, 3],
    [1/5, 1/3, 1]
])

# 3 suppliers scored on each criterion
ranking = topsis(
    [[80, 90, 85], [70, 85, 90], [85, 80, 70]],
    weights,
    ['benefit', 'benefit', 'benefit']
)
print(f"Best supplier: Supplier {ranking[0] + 1}")
```

### Step 4: Store Bicycles (Module 5)

Where do you put them in your shop?

```python
from supplycm.warehouse import warehouse_slotting_abc

bikes = [
    ('Mountain Bike', 50, 2),
    ('Road Bike', 30, 2),
    ('Kids Bike', 20, 1),
    ('BMX', 10, 1),
]

slotting = warehouse_slotting_abc(bikes, num_zones=3)
for bike, zone in slotting:
    print(f"{bike}: Zone {zone}")
```

### Step 5: Deliver to Customers (Module 6)

When customers order online, how do you deliver?

```python
from supplycm.routing import tsp_nearest_neighbor

# 4 customers to deliver to
distances = [
    [0, 5, 8, 12],
    [5, 0, 6, 10],
    [8, 6, 0, 4],
    [12, 10, 4, 0]
]

route, total = tsp_nearest_neighbor(distances)
print(f"Delivery route: {route}")
print(f"Total distance: {total} km")
```

### Step 6: Ensure Quality (Module 7)

Are the bicycles good quality?

```python
from supplycm.quality import dpmo, sigma_level

# 500 bikes, each with 10 quality checks, 5 defects found
dpmo_value = dpmo(5, 500, 10)
sigma = sigma_level(dpmo_value)
print(f"DPMO: {dpmo_value}")
print(f"Sigma level: {sigma}")
```

### Step 7: Work Efficiently (Module 8)

Is your shop running efficiently?

```python
from supplycm.lean import takt_time, oee

# Shop open 8 hours = 480 min, demand = 10 bikes per day
takt = takt_time(480, 10)
print(f"Takt time: {takt} minutes per bike")

# Machine availability 85%, performance 90%, quality 95%
oee_value = oee(0.85, 0.90, 0.95)
print(f"OEE: {oee_value*100:.1f}%")
```

### Step 8: Plan Monthly (Module 9)

How do you balance supply and demand?

```python
from supplycm.sop import production_chase_strategy, production_level_strategy

demand = [10, 12, 15, 14, 11, 13]  # bikes per month
print(f"Chase plan: {production_chase_strategy(demand)}")
print(f"Level plan: {production_level_strategy(demand)}")
```

### Step 9: Make Deals (Module 10)

What contract do you sign with your supplier?

```python
from supplycm.contracts import revenue_sharing_contract

result = revenue_sharing_contract(
    wholesale_price=150,
    retail_price=300,
    revenue_share_fraction=0.15,
    demand=1700,
    unit_cost=100
)
print(f"Supplier profit: ${result['supplier_profit']}")
print(f"Your profit: ${result['retailer_profit']}")
```

### Step 10: Be Green (Module 11)

How much CO2 do your deliveries produce?

```python
from supplycm.sustainability import carbon_footprint_transport

# Deliver 1700 bikes, average 10 km each, 15 kg per bike
co2 = carbon_footprint_transport(10, 1700 * 0.015)  # 0.015 tonnes = 15 kg
print(f"Annual delivery CO2: {co2:.0f} kg")
```

## The Full Picture

Here is how all the modules connect:

```
1. Forecast demand
     |
     v
2. Calculate inventory needs (EOQ, safety stock)
     |
     v
3. Choose suppliers (AHP, TOPSIS)
     |
     v
4. Sign contracts (revenue sharing, buyback)
     |
     v
5. Store in warehouse (ABC slotting)
     |
     v
6. Deliver to customers (TSP, VRP)
     |
     v
7. Check quality (DPMO, control charts)
     |
     v
8. Improve efficiency (Lean, OEE)
     |
     v
9. Plan next month (S&OP)
     |
     v
10. Reduce environmental impact (carbon footprint)
     |
     v
Back to step 1 (continuous improvement)
```

## Your Turn

Now apply this to your own scenario. Pick a product you are interested in:

1. Forecast its demand
2. Calculate how much to order
3. Pick a supplier
4. Decide on a contract
5. Plan your warehouse
6. Plan your delivery routes
7. Set quality targets
8. Calculate efficiency
9. Make a monthly plan
10. Check your environmental impact

## Final Quiz

Test your knowledge of the whole course:

1. What is the EOQ formula?
2. What does DPMO stand for?
3. What is the difference between chase and level production?
4. Name 3 types of supply chain contracts.
5. What does OEE measure?
6. What is takt time?
7. What is the formula for carbon footprint?
8. What is double marginalization?
9. What are the 5 steps of a supply chain?
10. What is the goal of Six Sigma?

<details>
<summary>Click to reveal answers</summary>

1. EOQ = square root of (2 x D x S / H)
2. Defects Per Million Opportunities
3. Chase: production matches demand. Level: constant production.
4. Revenue sharing, buyback, quantity flexibility
5. Overall Equipment Effectiveness (how well equipment is used)
6. The pace of customer demand (available time / demand)
7. CO2 = distance x weight x emission factor
8. When both supplier and retailer add margins, price is too high
9. Plan, Source, Make, Deliver, Return
10. 3.4 defects per million (99.99966% perfect)

</details>

## Congratulations!

You have completed the supplycm learning course. You now understand:

- How to forecast demand
- How to manage inventory
- How to work with suppliers
- How to organize warehouses
- How to plan delivery routes
- How to ensure quality
- How to work efficiently
- How to plan monthly operations
- How to make deals with suppliers
- How to reduce environmental impact

Keep practicing with the supplycm package. The more you use it, the better you will understand supply chain management.

## Where to Go Next

- Read the [supplycm documentation](https://github.com/atqatq/supplycm) for more algorithms
- Try the [exercises](../exercises/) in this repo
- Take the [quizzes](../quizzes/) to test yourself
- Check the [glossary](../glossary.md) for any terms you forgot
- Use the [cheat sheet](../cheatsheet.md) for quick reference

Happy learning!
