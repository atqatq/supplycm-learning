---
title: "Route Optimization Exercise | TSP and VRP Practice"
description: "Practice transportation routing: solve TSP with nearest neighbor and 2-opt. Vehicle routing problem exercise."
keywords: "routing exercise, TSP practice, VRP, route optimization, nearest neighbor, 2-opt"
---

# Exercise 6: Transportation

## Problem

You need to deliver to 5 customers. Distances between locations (in km):

| From\To | 0 (Depot) | 1 | 2 | 3 | 4 |
|---------|-----------|---|---|---|---|
| 0 | 0 | 10 | 15 | 20 | 25 |
| 1 | 10 | 0 | 35 | 25 | 30 |
| 2 | 15 | 35 | 0 | 30 | 20 |
| 3 | 20 | 25 | 30 | 0 | 15 |
| 4 | 25 | 30 | 20 | 15 | 0 |

### Tasks

1. Find a route using nearest neighbor
2. Improve it with 2-opt
3. What is the total distance for each?

## Your Answer

```
Nearest neighbor route: ___
Nearest neighbor distance: ___

2-opt route: ___
2-opt distance: ___
```

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.routing import tsp_nearest_neighbor, tsp_two_opt

distances = [
    [0, 10, 15, 20, 25],
    [10, 0, 35, 25, 30],
    [15, 35, 0, 30, 20],
    [20, 25, 30, 0, 15],
    [25, 30, 20, 15, 0],
]

route1, dist1 = tsp_nearest_neighbor(distances)
print(f"Nearest neighbor: {route1}, distance: {dist1}")

route2, dist2 = tsp_two_opt(distances)
print(f"2-opt: {route2}, distance: {dist2}")
print(f"Improvement: {((dist1 - dist2) / dist1 * 100):.1f}%")
```

</details>
