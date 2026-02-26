---
title: "Kruskal's Minimum Spanning Tree | supplycm Algorithm Library"
description: "Plain-English explanation of kruskal_mst from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, kruskal_mst, supply chain, plain english, networks"
---

# Kruskal's Minimum Spanning Tree

> **Call it:** `from supplycm.network import kruskal_mst` · **Level:** Intermediate · **You need:** basic arithmetic only

Connect all nodes with the cheapest possible set of links: sort every edge by cost, keep adding the cheapest that doesn't create a loop, stop when everything's connected. The result is the minimum spanning tree - maximum network for minimum pavement.

**Think of it like this:** Designing the cheapest road network connecting all villages: build the cheapest roads first, skip any that would make a pointless loop.

## When to reach for it

- Cheapest physical connection: pipelines, LAN, district heating
- Baseline network design before adding redundancy

## Try it with supplycm

```python
from supplycm.network import kruskal_mst

result = kruskal_mst(num_nodes=3, edges=[(0, 1, 4), (1, 2, 1), (0, 2, 2)])
print(result)
```

You should see something like:

```text
[[[1, 2, 1], [0, 2, 2]], 3.0]
```

Kept edges and total cost 3 - the expensive direct edge lost to the cheap detour; loops were refused by construction.

## Check yourself

1. Why does refusing loops guarantee optimality?
2. What does the MST minimize - and what not?
3. Why is a tree risky for operations?

<details>
<summary>Show answers</summary>

1. Any loop's priciest edge is redundant - Kruskal's never-create-a-loop rule quietly enforces that logic.

2. Total connection cost - NOT distances or failure risk; those need extra edges beyond the tree.

3. No redundancy - cut any edge and the network splits; MSTs are cheap, not resilient.

</details>

## Try this now

Build the MST for 5 nodes with competing edges; then add one backup edge and quantify the resilience you bought.

---
[← Min-Weight Bipartite Matching](min_weight_bipartite_matching.md) · [Back to Networks library](README.md) · [Prim's Minimum Spanning Tree →](prim_mst.md)

*New to this topic? Start with the core lesson first: [06_transportation.md](../../modules/06_transportation.md).*
