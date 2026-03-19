---
title: "TSP Held-Karp (Exact) | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_held_karp from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_held_karp, supply chain, plain english, routing & transportation"
---

# TSP Held-Karp (Exact)

> **Call it:** `from supplycm.routing import tsp_held_karp` · **Level:** Advanced · **You need:** basic arithmetic only

The exact TSP algorithm: dynamic programming over subsets guarantees the optimal tour. The price is exponential growth - fine for about a dozen stops, impossible for a hundred. Use it to find TRUE optimal answers on small instances and to calibrate how good your heuristics are.

**Think of it like this:** Solving a small maze perfectly on paper: with twelve junctions you can brute-force every sensible path - with a thousand, you'd need heuristics and humility.

## When to reach for it

- Ground-truth optimal tours for small stop sets
- Benchmarking heuristic quality (% above optimal)

## Try it with supplycm

```python
from supplycm.routing import tsp_held_karp

result = tsp_held_karp(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]])
print(result)
```

You should see something like:

```text
[[0, 2, 3, 1, 0, 0], 80]
```

The optimal tour and distance - run nearest-neighbor + 2-opt on the same matrix and see how close practice gets to proof.

## Check yourself

1. Why can't Held-Karp scale to 100 stops?
2. What is it actually FOR, then?
3. What runs on big instances in practice?

<details>
<summary>Show answers</summary>

1. It stores best costs for every (subset, endpoint) pair - 2^n subsets explode past n = 20-ish into memory oblivion.

2. Truth on small cases: knowing the optimal answer tells you your heuristic is 4% or 40% off - calibration.

3. Heuristics and metaheuristics (Lin-Kernighan style), which routinely land within a percent or two of optimal.

</details>

## Try this now

Solve a 6-city instance exactly with Held-Karp; then compare nearest-neighbor+2-opt and compute the gap percentage.

---
[← TSP Farthest Insertion](tsp_farthest_insertion.md) · [Back to Routing & Transportation library](README.md) · [TSP Christofides Algorithm →](tsp_christofides.md)
