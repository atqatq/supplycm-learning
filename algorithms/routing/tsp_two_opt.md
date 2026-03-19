---
title: "TSP 2-Opt Improvement | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_two_opt from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_two_opt, supply chain, plain english, routing & transportation"
---

# TSP 2-Opt Improvement

> **Call it:** `from supplycm.routing import tsp_two_opt` · **Level:** Beginner · **You need:** basic arithmetic only

Take any route and ask: would swapping two legs untangle a crossing? 2-opt removes two edges, reconnects the tour the better way, and repeats until no swap helps. It flattens the visual crossings in your route - and the savings are immediate and honest.

**Think of it like this:** Untangling a garden hose: find any place it crosses itself, uncross it - repeat until nothing crosses; water flows shorter.

## When to reach for it

- Improving routes from any construction heuristic
- The 5-minute fix that typically shaves 5-15% off distance

## Try it with supplycm

```python
from supplycm.routing import tsp_two_opt

result = tsp_two_opt(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]], initial_route=[0, 1, 3, 2], max_iter=1000)
print(result)
```

You should see something like:

```text
[[0, 1, 3, 2], 65]
```

An improved route and its distance - feed it the nearest-neighbor tour and watch the crossings untangle numerically.

## Check yourself

1. What swap does 2-opt perform?
2. Why do crossing edges signal improvement available?
3. 2-opt's weakness?

<details>
<summary>Show answers</summary>

1. Delete two edges, reconnect the two resulting paths the opposite way - reversing the segment between the cut points.

2. Triangle inequality: uncrossed shortcuts always exist - crossings are visible proof of wasted distance.

3. It gets trapped in local optima - no single swap helps anymore, but a bigger rearrangement might; that's where 3-opt and metaheuristics enter.

</details>

## Try this now

Draw a 5-point tour with one crossing, apply 2-opt logic by eye, then verify the distance drop with the function.

---
[← TSP Nearest Neighbor](tsp_nearest_neighbor.md) · [Back to Routing & Transportation library](README.md) · [TSP 3-Opt Improvement →](tsp_three_opt.md)
