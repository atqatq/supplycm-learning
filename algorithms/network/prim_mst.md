---
title: "Prim's Minimum Spanning Tree | supplycm Algorithm Library"
description: "Plain-English explanation of prim_mst from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, prim_mst, supply chain, plain english, networks"
---

# Prim's Minimum Spanning Tree

> **Call it:** `from supplycm.network import prim_mst` · **Level:** Intermediate · **You need:** basic arithmetic only

Kruskal's rival with a different strategy: grow ONE connected cluster from a start node, always adding the cheapest edge that reaches a new node. Same optimal total cost as Kruskal, different construction - and handier when you add nodes incrementally.

**Think of it like this:** Building a road network outward from the capital: at each step, extend to the nearest unconnected village - the network stays whole while it grows.

## When to reach for it

- Incremental network growth from an existing hub
- Same MST answers as Kruskal, with a growing-cluster story

## Try it with supplycm

```python
from supplycm.network import prim_mst

result = prim_mst(graph={0: [(1, 4), (2, 1)], 1: [(3, 1)], 2: [(1, 2), (3, 5)], 3: []}, start=0)
print(result)
```

You should see something like:

```text
[[[0, 2, 1], [2, 1, 2], [1, 3, 1]], 4.0]
```

The chosen edges and total cost - note how each step grabbed the cheapest link OUT of the growing cluster, never a loop.

## Check yourself

1. Prim vs Kruskal - when does each feel natural?
2. Does the start node change the total cost?
3. When would the two algorithms choose DIFFERENT edge sets?

<details>
<summary>Show answers</summary>

1. Prim grows from a hub (operations love it); Kruskal sorts all edges globally (planners love it) - same optimum, different story.

2. No - the MST cost is unique even when edge choices tie; start wherever you like.

3. On ties - multiple optimal trees can exist; both are equally cheap.

</details>

## Try this now

Run both algorithms on the same network; compare edge sets and totals, and explain any tie-breaking drama.

---
[← Kruskal's Minimum Spanning Tree](kruskal_mst.md) · [Back to Networks library](README.md) · [Ford-Fulkerson Max Flow →](ford_fulkerson_max_flow.md)
