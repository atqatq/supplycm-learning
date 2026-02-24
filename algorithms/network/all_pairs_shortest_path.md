---
title: "All-Pairs Shortest Path | supplycm Algorithm Library"
description: "Plain-English explanation of all_pairs_shortest_path from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, all_pairs_shortest_path, supply chain, plain english, networks"
---

# All-Pairs Shortest Path

> **Call it:** `from supplycm.network import all_pairs_shortest_path` · **Level:** Advanced · **You need:** basic arithmetic only

Instead of one origin, run shortest paths between EVERY pair of nodes in one structured pass. The result is a full distance table - the complete 'cost to go from anywhere to anywhere' matrix that planning systems feed on.

**Think of it like this:** A train timetable's master fare chart: every station to every station, one authoritative grid instead of a hundred separate queries.

## When to reach for it

- Distance matrices for VRP and facility-location models
- Any planning step that repeatedly asks 'how far from X to Y?'

## Try it with supplycm

```python
from supplycm.network import all_pairs_shortest_path

result = all_pairs_shortest_path(graph={0: [(1, 4), (2, 1)], 1: [(3, 1)], 2: [(1, 2), (3, 5)], 3: []}, nodes=[0, 1, 2, 3])
print(result)
```

You should see something like:

```text
{0: {0: 0.0, 1: 3.0, 2: 1.0, 3: 4.0}, 1: {0: inf, 1: 0.0, 2: inf, 3: 1.0}, 2: {0: inf, 1: 2.0, 2: 0.0, 3: 3.0}, 3: {0: inf, 1: inf, 2: inf, 3: 0.0}}
```

A nested dict: distances[from][to] - the complete cost map; note the unreachable pairs marked as infinity.

## Check yourself

1. When would you precompute all pairs instead of on-demand queries?
2. What do infinite entries mean?
3. Directed vs undirected - how does it show here?

<details>
<summary>Show answers</summary>

1. When many downstream models (routing, location) will query constantly - compute once, reuse everywhere.

2. Unreachable pairs - no directed path exists; a red flag in supply networks worth investigating.

3. One-way lanes produce asymmetric tables - cheap going, impossible returning; real road networks hide these surprises.

</details>

## Try this now

Build a small one-way street network and find the asymmetric pairs; explain who can't get home directly.

---
[← Bellman-Ford](bellman_ford.md) · [Back to Networks library](README.md) · [Floyd-Warshall →](floyd_warshall.md)
