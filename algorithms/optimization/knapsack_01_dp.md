---
title: "0-1 Knapsack (Dynamic Programming) | supplycm Algorithm Library"
description: "Plain-English explanation of knapsack_01_dp from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, knapsack_01_dp, supply chain, plain english, optimization"
---

# 0-1 Knapsack (Dynamic Programming)

> **Call it:** `from supplycm.optimization import knapsack_01_dp` · **Level:** Intermediate · **You need:** basic arithmetic only

The indivisible version: each item is taken fully or not at all, and greedy density famously fails. Dynamic programming builds a table of best values for every capacity - careful, exact, and the textbook door into DP thinking.

**Think of it like this:** Packing a carry-on: each gadget goes wholly or stays home - the camera's bulk and the drone's value interact, so you plan combinations, not just rankings.

## When to reach for it

- Discrete selection under one constraint (SKUs, projects, features)
- The canonical example for learning dynamic programming

## Try it with supplycm

```python
from supplycm.optimization import knapsack_01_dp

result = knapsack_01_dp(weights=[10, 20, 30], values=[60, 100, 120], capacity=50)
print(result)
```

You should see something like:

```text
[220, [1, 2]]
```

Best value 220 with items 1 and 2 - the dense-but-awkward combination beats greedy's first pick; the table saw it coming.

## Check yourself

1. Why does greedy fail on 0-1 knapsack?
2. What does the DP table remember?
3. What grows painfully here?

<details>
<summary>Show answers</summary>

1. Density ignores leftover SPACE - the best-density item can strand capacity the second-best would have filled perfectly.

2. The best achievable value for every (items so far, capacity) combination - no scenario is ever recomputed or forgotten.

3. Capacity range and item count - the table's size is their product; huge capacities need different machinery.

</details>

## Try this now

Add a 4th item of weight 10, value 70; recompute and find the new optimal set by hand before verifying.

---
[← Fractional Knapsack](fractional_knapsack.md) · [Back to Optimization library](README.md) · [Subset Sum →](subset_sum.md)
