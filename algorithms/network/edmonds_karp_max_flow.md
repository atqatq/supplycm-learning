---
title: "Edmonds-Karp Max Flow | supplycm Algorithm Library"
description: "Plain-English explanation of edmonds_karp_max_flow from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, edmonds_karp_max_flow, supply chain, plain english, networks"
---

# Edmonds-Karp Max Flow

> **Call it:** `from supplycm.network import edmonds_karp_max_flow` · **Level:** Advanced · **You need:** basic arithmetic only

Ford-Fulkerson with discipline: always augment along the FEWEST-hops remaining path (BFS choice). That one rule bounds the runtime and makes the method predictable - same max flow, professionally punctual.

**Think of it like this:** Same flood-the-highways plan, but trucks always take the route with the fewest toll booths first - tidy, predictable, provably fast.

## When to reach for it

- Reliable max-flow computation without algorithmic surprises
- The standard classroom-and-production choice for max flow

## Try it with supplycm

```python
from supplycm.network import edmonds_karp_max_flow

result = edmonds_karp_max_flow(capacity=[[0, 5, 0, 0], [0, 0, 4, 3], [0, 0, 0, 2], [0, 0, 0, 0]], source=0, sink=3)
print(result)
```

You should see something like:

```text
5.0
```

The same maximum flow - reached via shortest augmenting paths; the value matches Ford-Fulkerson, guaranteed.

## Check yourself

1. What did Edmonds-Karp actually add?
2. Why does BFS-based choice help?
3. Max flow answers capacity - what question comes next?

<details>
<summary>Show answers</summary>

1. A rule: always the shortest augmenting path - turning 'it works' into 'it works in bounded time'.

2. Short paths saturate quickly and don't zigzag - the number of augmentations stays provably small.

3. Minimum cost of achieving that flow - which is exactly the min-cost-flow family's business.

</details>

## Try this now

Compare augmentation orders of plain FF and EK on a small network; count the rounds each took.

---
[← Ford-Fulkerson Max Flow](ford_fulkerson_max_flow.md) · [Back to Networks library](README.md) · [Min-Cut / Max-Flow Theorem →](min_cut_max_flow_theorem.md)
