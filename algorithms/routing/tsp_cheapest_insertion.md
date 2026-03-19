---
title: "TSP Cheapest Insertion | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_cheapest_insertion from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_cheapest_insertion, supply chain, plain english, routing & transportation"
---

# TSP Cheapest Insertion

> **Call it:** `from supplycm.routing import tsp_cheapest_insertion` · **Level:** Intermediate · **You need:** basic arithmetic only

Insertion with a sharper eye: instead of choosing the city closest to the tour, choose the (city, gap) PAIR with the smallest insertion cost anywhere. Slightly more work per step, consistently slightly better tours - the connoisseur's insertion.

**Think of it like this:** Hiring for a team: don't just consider the best candidate available - consider the best CANDIDATE-INTO-SEAT combination, filling the costliest gap first.

## When to reach for it

- Tour construction where a little extra care pays
- The default seed for many practical VRP pipelines

## Try it with supplycm

```python
from supplycm.routing import tsp_cheapest_insertion

result = tsp_cheapest_insertion(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]])
print(result)
```

You should see something like:

```text
[[0, 2, 3, 1, 0], 80]
```

The grown tour and its cost - each step picked the globally cheapest city-into-gap move, not merely the nearest city.

## Check yourself

1. Nearest vs cheapest insertion - the precise difference?
2. Why is cheapest usually better?
3. What do both share with all insertion methods?

<details>
<summary>Show answers</summary>

1. Nearest picks by CITY proximity to the tour; cheapest scans all (city, position) pairs by insertion COST.

2. It evaluates the actual increment - a nearby city might only fit badly, while a slightly farther one slots in for pennies.

3. They maintain valid complete tours at every step - you could stop mid-way and still have a usable route.

</details>

## Try this now

Run both insertion variants on a 6-point matrix; find the step where they disagree and who won.

---
[← TSP Nearest Insertion](tsp_nearest_insertion.md) · [Back to Routing & Transportation library](README.md) · [TSP Farthest Insertion →](tsp_farthest_insertion.md)
