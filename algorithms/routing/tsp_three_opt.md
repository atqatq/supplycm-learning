---
title: "TSP 3-Opt Improvement | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_three_opt from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_three_opt, supply chain, plain english, routing & transportation"
---

# TSP 3-Opt Improvement

> **Call it:** `from supplycm.routing import tsp_three_opt` · **Level:** Advanced · **You need:** basic arithmetic only

2-opt with a wider reach: cut THREE edges and try all smarter reconnections - including segment moves 2-opt can't express. More powerful escapes from local optima, at a higher price per iteration. The classic middle ground before metaheuristics.

**Think of it like this:** 2-opt uncrosses two strands; 3-opt can also REORDER whole chunks of the route - like rearranging paragraphs, not just fixing crossings.

## When to reach for it

- Squeezing the last percent from good tours
- Upgrading a 2-opt pipeline that has plateaued

## Try it with supplycm

```python
from supplycm.routing import tsp_three_opt

result = tsp_three_opt(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]], initial_route=[0, 1, 3, 2], max_iter=100)
print(result)
```

You should see something like:

```text
[[0, 1, 3, 2], 65]
```

A refined tour and distance - on richer instances it finds moves 2-opt is structurally blind to.

## Check yourself

1. What can 3-opt do that 2-opt can't?
2. Why not always run 3-opt?
3. How do you escape 3-opt's local optimum?

<details>
<summary>Show answers</summary>

1. Reconnect three cut pieces in genuinely different ORDERS - relocating segments, not just uncrossing them.

2. It explores many more reconnection cases per move - the cost shows on large routes and time-pressured dispatch.

3. Random restarts, perturbation (ruin-and-recreate), or metaheuristics - accept moves that temporarily worsen.

</details>

## Try this now

Compare 2-opt and 3-opt final distances on a 12-point random tour; quantify what the third cut bought.

---
[← TSP 2-Opt Improvement](tsp_two_opt.md) · [Back to Routing & Transportation library](README.md) · [TSP Nearest Insertion →](tsp_nearest_insertion.md)
