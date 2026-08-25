---
title: "S&OP Exercise | Chase vs Level Production Strategy"
description: "Practice Sales and Operations Planning: compare chase and level production strategies."
keywords: "S&OP exercise, chase strategy, level strategy, production planning, demand supply matching"
---

# Exercise 9: S&OP

## Problem

Your demand forecast for 6 months:

| Month | Demand |
|-------|--------|
| Jan | 500 |
| Feb | 600 |
| Mar | 800 |
| Apr | 1000 |
| May | 900 |
| Jun | 700 |

### Tasks

1. Calculate the level production plan
2. Calculate the chase production plan
3. Which would you choose for ice cream? Why?

## Your Answer

```
Level plan: ___
Chase plan: ___
Choice: ___
Reason: ___
```

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.sop import production_level_strategy, production_chase_strategy

demand = [500, 600, 800, 1000, 900, 700]

level = production_level_strategy(demand)
chase = production_chase_strategy(demand)

print(f"Level plan: {level}")
print(f"Chase plan: {chase}")
```

### Expected Results

1. Level plan: [750, 750, 750, 750, 750, 750] (average of all months)
2. Chase plan: [500, 600, 800, 1000, 900, 700] (matches demand)
3. For ice cream: Chase strategy, because ice cream is perishable and demand is very seasonal

</details>
