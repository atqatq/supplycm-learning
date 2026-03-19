---
title: "TSP Farthest Insertion | supplycm Algorithm Library"
description: "Plain-English explanation of tsp_farthest_insertion from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, tsp_farthest_insertion, supply chain, plain english, routing & transportation"
---

# TSP Farthest Insertion

> **Call it:** `from supplycm.routing import tsp_farthest_insertion` · **Level:** Intermediate · **You need:** basic arithmetic only

The counterintuitive one: repeatedly insert the city FARTHEST from the tour, placing it in its cheapest gap. Get the difficult, distant places locked in early; near ones slot in trivially later. Often beats nearest insertion on scattered geographies.

**Think of it like this:** Furnishing a studio: place the awkward oversized pieces first - the small lamps fit anywhere afterwards.

## When to reach for it

- Geographically spread stop sets with clear outliers
- An alternative seed when nearest-insertion tours underwhelm

## Try it with supplycm

```python
from supplycm.routing import tsp_farthest_insertion

result = tsp_farthest_insertion(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]])
print(result)
```

You should see something like:

```text
[[1, 3, 2, 0, 1], 80]
```

The tour and cost - the remote stops got skeletonized early, and the close ones filled in around them.

## Check yourself

1. Why would FARTHEST first help?
2. When does farthest insertion shine?
3. Is any insertion rule universally best?

<details>
<summary>Show answers</summary>

1. Distant cities constrain the tour's shape most - fixing their placement early prevents costly detours later.

2. Clustered stops with far outliers - the outliers define the tour's rough outline instantly.

3. No - instance-dependent; that's why pipelines try several seeds and keep the best after improvement.

</details>

## Try this now

Build a matrix with two tight clusters and one far outlier; compare nearest vs farthest insertion tours.

---
[← TSP Cheapest Insertion](tsp_cheapest_insertion.md) · [Back to Routing & Transportation library](README.md) · [TSP Held-Karp (Exact) →](tsp_held_karp.md)
