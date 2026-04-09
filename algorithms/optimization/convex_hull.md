---
title: "Convex Hull | supplycm Algorithm Library"
description: "Plain-English explanation of convex_hull from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, convex_hull, supply chain, plain english, optimization"
---

# Convex Hull

> **Call it:** `from supplycm.optimization import convex_hull` · **Level:** Intermediate · **You need:** basic arithmetic only

Stretch a rubber band around all your points: the band's shape is the convex hull - the tightest boundary containing everything. It defines the OUTLINE of a facility footprint, a demand region, or a route territory in one clean polygon.

**Think of it like this:** Placing a rubber band around pushpins on a board: it snaps tight around the outermost pins - the inner ones just sit inside the shape.

## When to reach for it

- Service territory outlines and demand-region boundaries
- Finding extreme locations: farthest points, boundary sites

## Try it with supplycm

```python
from supplycm.optimization import convex_hull

result = convex_hull(points=[(0, 0), (1, 1), (2, 0), (1, -1), (0.5, 0.5)])
print(result)
```

You should see something like:

```text
[[0, 0], [1, -1], [2, 0], [1, 1]]
```

The boundary points in order - note (0.5, 0.5) and (1, 1) dropped out: inner points never touch the rubber band.

## Check yourself

1. What does an interior point mean for delivery territory?
2. Why do hulls help network design?
3. What's the 'turn' test that builds the hull?

<details>
<summary>Show answers</summary>

1. It's covered by the boundary - no special planning needed; the hull defines where service must reach.

2. They bound the geography - perimeter, diameter, and hull area estimate travel effort before any routing.

3. Walking the boundary, every turn must lean the same way - any reverse turn means a point hides inside and gets ejected.

</details>

## Try this now

Plot 8 invented points, draw the hull by eye, then verify - including which interior points the band ignored.

---
[← Matrix Chain Multiplication](matrix_chain_multiplication.md) · [Back to Optimization library](README.md) · [Graph Coloring (Greedy) →](graph_coloring_greedy.md)
