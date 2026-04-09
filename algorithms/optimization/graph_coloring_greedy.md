---
title: "Graph Coloring (Greedy) | supplycm Algorithm Library"
description: "Plain-English explanation of graph_coloring_greedy from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, graph_coloring_greedy, supply chain, plain english, optimization"
---

# Graph Coloring (Greedy)

> **Call it:** `from supplycm.optimization import graph_coloring_greedy` · **Level:** Intermediate · **You need:** basic arithmetic only

Assign 'colors' so no two connected nodes share one: exam timetables (no student sits two exams at once), shift assignments, channel allocation. Greedy processes nodes one by one, grabbing the first legal color - simple, quick, occasionally one color shy of optimal.

**Think of it like this:** Seating feuding families at a wedding: each guest takes the first table without an enemy - orderly enough, though a wiser seating might use fewer tables.

## When to reach for it

- Timetabling and conflict-free scheduling
- Any 'conflicting items can't coincide' assignment

## Try it with supplycm

```python
from supplycm.optimization import graph_coloring_greedy

result = graph_coloring_greedy(graph={0: [1, 2], 1: [0, 2], 2: [0, 1], 3: [4], 4: [3]})
print(result)
```

You should see something like:

```text
{0: 0, 1: 1, 2: 2, 3: 0, 4: 1}
```

A color per node - the triangle needs three; the separate pair reuses color 0, showing how components recycle palettes.

## Check yourself

1. What do 'colors' represent in scheduling?
2. Why can greedy use more colors than necessary?
3. What's the theoretical floor on colors?

<details>
<summary>Show answers</summary>

1. Time slots, rooms, or resources - any dimension where conflicting items must separate.

2. Order matters - an unlucky sequence forces early colors a better order would avoid; the clique of conflicts sets the true floor.

3. The largest fully-connected group (clique) needs that many colors - count the triangle, and three is unavoidable.

</details>

## Try this now

Reorder the node processing and see if the color count drops; find the order that wastes the least.

---
[← Convex Hull](convex_hull.md) · [Back to Optimization library](README.md) · [N-Queens Backtracking →](n_queens_backtracking.md)
