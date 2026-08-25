---
title: "Sales and Operations Planning (S&OP) Tutorial"
description: "Learn S&OP: demand-supply matching, chase production strategy, level production strategy, and the monthly S&OP cycle."
keywords: "S&OP, sales and operations planning, chase strategy, level strategy, demand planning, supply planning, production planning"
---

# Module 9: Planning Ahead (S&OP)

## The Big Idea

S&OP stands for Sales and Operations Planning. It is a monthly process where different parts of a company agree on one plan.

## Why Does It Matter?

Without S&OP, departments fight:

- Sales wants high inventory (never run out)
- Finance wants low inventory (save money)
- Production wants stable output (no overtime)

S&OP brings everyone together to make one plan that balances these goals.

## The S&OP Cycle

S&OP happens every month in 5 steps:

### Step 1: Update Forecast
Look at what sold last month. Update the demand forecast.

### Step 2: Demand Planning
Sales team reviews the forecast. They add knowledge about promotions, new products, etc.

### Step 3: Supply Planning
Production team checks if they can make what sales wants. They identify constraints.

### Step 4: Reconciliation
Compare demand and supply. Find gaps. Decide how to close them.

### Step 5: Executive Review
Leaders approve the plan. Everyone commits to it.

## Demand-Supply Matching

The core of S&OP is comparing what customers want with what you can make.

### Try it with supplycm

```python
from supplycm.sop import demand_supply_match

demand = [100, 120, 130, 110, 125]
supply = [110, 110, 130, 130, 130]

net, cumulative = demand_supply_match(demand, supply)
print(f"Net demand: {net}")
print(f"Cumulative gap: {cumulative}")
# Positive = shortage, Negative = surplus
```

## Production Strategies

When demand goes up and down, you have two main strategies:

### Chase Strategy: Match Production to Demand

Produce exactly what customers want each period.

**Pros:** Low inventory
**Cons:** Workforce fluctuates (hiring/firing)

### Try it with supplycm

```python
from supplycm.sop import production_chase_strategy

demand = [100, 120, 130, 110, 125]
production = production_chase_strategy(demand)
print(f"Production plan: {production}")
# Produces exactly the demand each period
```

### Level Strategy: Constant Production

Produce the same amount every period. Inventory absorbs the difference.

**Pros:** Stable workforce
**Cons:** Higher inventory

### Try it with supplycm

```python
from supplycm.sop import production_level_strategy

demand = [100, 120, 130, 110, 125]
production = production_level_strategy(demand)
print(f"Production plan: {production}")
# Produces the average every period
```

## Comparing Strategies

| Aspect | Chase | Level |
|--------|-------|-------|
| Inventory | Low | High |
| Workforce stability | Low | High |
| Hiring/firing cost | High | Low |
| Overtime | Low | May need overtime |
| Best for | Perishable goods | Stable workforce needs |

## The S&OP Meeting

Once a month, leaders meet to review:

1. Did we hit last month's plan?
2. What changed in the forecast?
3. Can we meet the new demand?
4. What trade-offs do we need to make?
5. What is the final plan?

Everyone leaves the meeting aligned on what to do.

## Quick Quiz

1. What does S&OP stand for?
2. What are the 5 steps of the S&OP cycle?
3. What is the difference between chase and level production?
4. When would you use chase strategy?

<details>
<summary>Click to reveal answers</summary>

1. Sales and Operations Planning
2. Update forecast, Demand planning, Supply planning, Reconciliation, Executive review
3. Chase: production matches demand. Level: constant production, inventory absorbs changes.
4. When inventory is expensive or products are perishable

</details>

## Exercise

You sell ice cream. Demand varies by season:

| Month | Demand |
|-------|--------|
| Jan | 500 |
| Feb | 600 |
| Mar | 800 |
| Apr | 1000 |
| May | 1500 |
| Jun | 2000 |

1. Calculate the level production rate
2. Calculate the chase production plan
3. Which strategy would you choose? Why?
4. What are the trade-offs?

## Key Words

- **S&OP**: Sales and Operations Planning
- **Chase strategy**: Production matches demand each period
- **Level strategy**: Constant production rate
- **Demand-supply match**: Comparing what is wanted with what can be made
- **Reconciliation**: Resolving gaps between demand and supply

## What's Next?

You have a plan. Now you need to make deals with suppliers. The next lesson is about contracts.

Next: [Module 10 - Making Deals (Contracts)](10_contracts.md)
