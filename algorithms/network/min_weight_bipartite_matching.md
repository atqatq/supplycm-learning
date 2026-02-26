---
title: "Min-Weight Bipartite Matching | supplycm Algorithm Library"
description: "Plain-English explanation of min_weight_bipartite_matching from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, min_weight_bipartite_matching, supply chain, plain english, networks"
---

# Min-Weight Bipartite Matching

> **Call it:** `from supplycm.network import min_weight_bipartite_matching` · **Level:** Advanced · **You need:** basic arithmetic only

The cost twin: every pairing has a PRICE (time, distance, effort), and you want the full assignment at MINIMUM total cost. Same math as the max version, opposite direction - the engine behind cheapest-optimal crew and job assignment.

**Think of it like this:** Hiring movers for rooms: every mover quotes different prices per room - the landlord picks the complete assignment with the smallest total quote.

## When to reach for it

- Cheapest full assignment of tasks to resources
- Cost-minimizing dispatch where every unit must be assigned

## Try it with supplycm

```python
from supplycm.network import min_weight_bipartite_matching

result = min_weight_bipartite_matching(cost_matrix=[[3, 1], [2, 4]])
print(result)
```

You should see something like:

```text
[[[1, 0], [0, 1]], 3.0]
```

The cheapest pairs and total cost 3 - the greedy 3+4 pick would cost 5; the clever 1+2 split wins.

## Check yourself

1. When do I use min-weight vs max-weight?
2. What if a pairing is impossible?
3. How does this relate to the Hungarian algorithm?

<details>
<summary>Show answers</summary>

1. Costs (minimize) vs benefits (maximize) - flip signs and they're the same algorithm wearing different clothes.

2. Set its cost to a huge number - effectively forbidden, and the math routes around it.

3. It IS the classic assignment problem - Hungarian is the famous solution method for exactly this.

</details>

## Try this now

Fill a 3x3 cost matrix from a real mini-scenario and verify the optimal total against your hand-tried best.

---
[← Max-Weight Bipartite Matching](max_weight_bipartite_matching.md) · [Back to Networks library](README.md) · [Kruskal's Minimum Spanning Tree →](kruskal_mst.md)
