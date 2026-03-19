---
title: "TSP Nearest Neighbor | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_nearest_neighbor from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_nearest_neighbor, supply chain, plain english, routing & transportation"
---

# TSP Nearest Neighbor

> **Call it:** `from supplycm.routing import tsp_nearest_neighbor` · **Level:** Beginner · **You need:** basic arithmetic only

The instinctive route builder: from your start, always drive to the CLOSIST unvisited stop, repeat until done, then return home. Two minutes to learn, instantly useful - and reliably 10-25% longer than the best route. The baseline every serious routing method must beat.

**Think of it like this:** Errand-running on autopilot: each time you finish a stop, you just roll to whichever next stop looks closest.

## When to reach for it

- Quick routes when 'pretty good now' beats 'perfect later'
- The benchmark for judging fancier TSP methods

## Try it with supplycm

```python
from supplycm.routing import tsp_nearest_neighbor

result = tsp_nearest_neighbor(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]], start=0)
print(result)
```

You should see something like:

```text
[[0, 1, 3, 2, 0], 80.0]
```

Route and total distance 80 - trace it: each step grabbed the nearest unvisited stop; the return leg may sting.

## Check yourself

1. Why can nearest neighbor paint itself into a corner?
2. Does the start city change the result?
3. Why keep it as a benchmark?

<details>
<summary>Show answers</summary>

1. Greedy closeness ignores the return trip - early cheap hops can force one horrific final leg.

2. Often, substantially - try each start on small problems; the best NN route is the best of those attempts.

3. It is free and instant - any fancier method must beat THIS to justify existing.

</details>

## Try this now

Run NN from all 4 starting cities on the example; rank the four totals and crown the luckiest start.

---
[Back to Routing & Transportation library](README.md) · [TSP 2-Opt Improvement →](tsp_two_opt.md)

*New to this topic? Start with the core lesson first: [06_transportation.md](../../modules/06_transportation.md).*
