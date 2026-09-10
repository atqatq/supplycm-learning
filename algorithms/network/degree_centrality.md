---
title: "Degree Centrality | supplycm Algorithm Library"
description: "Plain-English explanation of degree_centrality from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, degree_centrality, supply chain, plain english, networks"
---

# Degree Centrality

> **Call it:** `from supplycm.network import degree_centrality` · **Level:** Beginner · **You need:** basic arithmetic only

The simplest popularity score: how many connections does each node have? Hubs with many links matter simply because so much can flow through them. One call ranks your network's social butterflies - a first, honest glance at structure.

**Think of it like this:** Counting friends at a party: the person talking with everyone is a hub - no deep math, just a headcount.

## When to reach for it

- First-pass hub identification
- Sanity checks before fancier centrality metrics

## Try it with supplycm

```python
from supplycm.network import degree_centrality

result = degree_centrality(graph={0: [1, 2], 1: [0, 3], 2: [0], 3: [1]}, num_nodes=4)
print(result)
```

You should see something like:

```text
{0: 0.6667, 1: 0.6667, 2: 0.3333, 3: 0.3333}
```

Shares per node - nodes 0 and 1 lead with two-thirds connectivity; nodes 2 and 3 are leaves leaning on their hubs.

## Check yourself

1. What does degree centrality MISS?
2. In supply networks, what does high degree suggest?
3. Why normalize by node count?

<details>
<summary>Show answers</summary>

1. Position: a node with 2 well-placed links can matter more than one with 5 in a corner - degree ignores location.

2. Consolidation - many flows share this node; efficient, but also concentrated risk.

3. So networks of different sizes compare fairly - a 3-link node in a tiny net isn't automatically a hub.

</details>

## Try this now

Rank 6 nodes by degree; then find the one whose REMOVAL hurts most and note it wasn't necessarily the top degree.

---
[← Bridges in Graph](bridges_in_graph.md) · [Back to Networks library](README.md) · [Closeness Centrality →](closeness_centrality.md)
