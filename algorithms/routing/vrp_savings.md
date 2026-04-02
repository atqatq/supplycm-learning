---
title: "Clarke-Wright Savings Algorithm | supplycm Algorithm Library"
description: "Plain-English explanation of vrp_savings from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, vrp_savings, supply chain, plain english, routing & transportation"
---

# Clarke-Wright Savings Algorithm

> **Call it:** `from supplycm.routing import vrp_savings` · **Level:** Intermediate · **You need:** basic arithmetic only

The classic CVRP builder with a beautiful idea: start with every customer on their own tiny out-and-back route, then MERGE pairs whenever merging saves distance - ranked by the 'savings' s(i,j) = cost(i,depot) + cost(depot,j) - cost(i,j). Big savings merge first, capacity permitting.

**Think of it like this:** Carpooling from a hub: everyone drives separately until you spot two neighbors whose combined trip is shorter than two separate ones - merge the biggest synergies first.

## When to reach for it

- Building complete CVRP solutions quickly
- The historically celebrated heuristic that still performs

## Try it with supplycm

```python
from supplycm.routing import vrp_savings

result = vrp_savings(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]], demands=[0, 1, 1, 1], vehicle_capacity=3)
print(result)
```

You should see something like:

```text
[[0, 2, 3, 1, 0]]
```

Merged routes - each merge happened because combining beat the two separate depot trips; the savings list is the algorithm's logic made visible.

## Check yourself

1. What exactly is a 'saving'?
2. Why does merging start from single-customer routes?
3. What constrains a merge?

<details>
<summary>Show answers</summary>

1. The distance NOT driven by joining i and j directly instead of both via the depot - the win from carpooling, numerically.

2. Because every route must eventually connect to the depot - starting fragmented makes every possible merge available.

3. Vehicle capacity and route-compatibility (i at the end of one route, j at the front of another) - savings you can't legally realize are skipped.

</details>

## Try this now

Compute the savings matrix by hand for 4 customers; execute the merges yourself and check the function agrees.

---
[← CVRP Greedy Insertion](vrp_capacitated_greedy.md) · [Back to Routing & Transportation library](README.md) · [VRP Sweep Algorithm →](vrp_sweep.md)
