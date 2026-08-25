---
title: "Supplier Selection Exercise | AHP and TOPSIS Practice"
description: "Practice supplier selection using AHP and TOPSIS methods. Includes step-by-step solution."
keywords: "supplier selection exercise, AHP practice, TOPSIS, supplier evaluation, procurement exercise"
---

# Exercise 4: Suppliers

## Problem

You need to choose a supplier for coffee beans. You have 3 options:

| Supplier | Price ($/lb) | Quality (1-10) | Delivery (days) |
|----------|-------------|----------------|-----------------|
| A | 5.00 | 8 | 7 |
| B | 4.50 | 6 | 5 |
| C | 6.00 | 9 | 10 |

### Tasks

1. Decide your criteria weights (what matters most?)
2. Use AHP to calculate weights
3. Use TOPSIS to rank suppliers
4. Which supplier do you choose?

## Your Answer

(Write your work here)

---

<details>
<summary>Click to reveal sample solution</summary>

### Using supplycm

```python
from supplycm.supplier import ahp_supplier_selection, topsis

# Step 1: Decide criteria and weights
# Price is most important, then quality, then delivery
pairwise = [
    [1, 2, 3],     # Price vs Quality, Price vs Delivery
    [1/2, 1, 2],   # Quality vs Price, Quality vs Delivery
    [1/3, 1/2, 1]  # Delivery vs Price, Delivery vs Quality
]
weights = ahp_supplier_selection(pairwise)
print(f"Weights: Price={weights[0]:.2f}, Quality={weights[1]:.2f}, Delivery={weights[2]:.2f}")

# Step 2: Score each supplier
# For price, lower is better, so we invert: 1/price * 100
# For quality and delivery, we use the scores directly (higher = better for quality, lower = better for delivery)
# Let us normalize: price -> 100/price, quality -> score*10, delivery -> 100/delivery

decision_matrix = [
    [100/5.00, 80, 100/7],  # Supplier A
    [100/4.50, 60, 100/5],  # Supplier B
    [100/6.00, 90, 100/10]  # Supplier C
]

ranking = topsis(decision_matrix, weights, ['benefit', 'benefit', 'benefit'])
print(f"Ranking: {ranking}")
print(f"Best supplier: Supplier {ranking[0] + 1}")
```

### Analysis

With price as the most important criterion, Supplier B (cheapest) might win. But if quality matters more, Supplier C could be best. The AHP + TOPSIS method gives you a systematic way to decide.

</details>
