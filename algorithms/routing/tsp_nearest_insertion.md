---
title: "TSP Nearest Insertion | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_nearest_insertion from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_nearest_insertion, supply chain, plain english, routing & transportation"
---

# TSP Nearest Insertion

> **Call it:** `from supplycm.routing import tsp_nearest_insertion` · **Level:** Intermediate · **You need:** basic arithmetic only

Grow the tour like a snowball: start with two cities, then repeatedly grab the unvisited city CLOSEST to the current tour and insert it where it costs least. Builds naturally good tours without the myopia of pure nearest-neighbor chains.

**Think of it like this:** Planning a dinner-party seating chart one guest at a time: invite the friend closest to the existing group, seat them in the gap that upsets the table least.

## When to reach for it

- Constructing decent tours before improvement passes
- When route GROWTH feels more natural than hop-by-hop chains

## Try it with supplycm

```python
from supplycm.routing import tsp_nearest_insertion

result = tsp_nearest_insertion(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]])
print(result)
```

You should see something like:

```text
[[0, 2, 3, 1, 0], 80]
```

A complete tour with its cost - compare with nearest-neighbor on the same matrix; the insertion logic often wins.

## Check yourself

1. How does insertion differ from nearest-neighbor construction?
2. Why does 'cheapest insertion point' matter?
3. What comes after insertion heuristics?

<details>
<summary>Show answers</summary>

1. NN extends a PATH hop by hop; insertion keeps a valid closed TOUR and grows it - never leaving loose ends.

2. The same city can join anywhere - slotting it into its least-disruptive gap preserves the tour's economy.

3. Improvement: 2-opt/3-opt polish - construction gives a good skeleton; improvement trims the fat.

</details>

## Try this now

Trace the growth on 5 cities: which city joined when, and where did it insert? Spot the moment the tour bent well.

---
[← TSP 3-Opt Improvement](tsp_three_opt.md) · [Back to Routing & Transportation library](README.md) · [TSP Cheapest Insertion →](tsp_cheapest_insertion.md)
