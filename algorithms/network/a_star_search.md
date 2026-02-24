---
title: "A* Search | supplycm Algorithm Library"
description: "Plain-English explanation of a_star_search from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, a_star_search, supply chain, plain english, networks"
---

# A* Search

> **Call it:** `from supplycm.network import a_star_search` · **Level:** Intermediate · **You need:** basic arithmetic only

Dijkstra with a hunch: A* adds a heuristic - an estimate of remaining distance to the goal - and explores in the direction of promise. With an honest (never-overestimating) hunch, it finds the optimal path while touching far fewer nodes. Dijkstra explores everywhere; A* explores toward the target.

**Think of it like this:** A bloodhound: instead of sniffing the whole forest, it leans toward where the fox likely went - guided searching, same guaranteed find.

## When to reach for it

- Point-to-point routing on large networks
- Any search where a decent goal estimate exists

## Try it with supplycm

```python
from supplycm.network import a_star_search

result = a_star_search(graph={0: [(1, 4), (2, 1)], 1: [(3, 1)], 2: [(1, 2), (3, 5)], 3: []}, start=0, goal=3, heuristic=lambda n: {0: 3, 1: 2, 2: 2, 3: 0}[n])
print(result)
```

You should see something like:

```text
[[0, 2, 1, 3], 4]
```

The optimal path with its cost - reached by examining mostly the nodes lying toward the goal, not the whole map.

## Check yourself

1. What makes a heuristic 'admissible'?
2. Heuristic of constant zero - what does A* become?
3. Why is A* the routing standard?

<details>
<summary>Show answers</summary>

1. It never overestimates the true remaining cost - optimism keeps A* from skipping the true best path.

2. Plain Dijkstra - the hunch is gone, so full exploration returns.

3. Road networks come with natural estimates (straight-line distance), and the savings are enormous.

</details>

## Try this now

Run A* with a wildly overestimating heuristic; observe how the 'optimal' path breaks - and why honesty matters.

---
[← Dijkstra's Shortest Path](dijkstra_shortest_path.md) · [Back to Networks library](README.md) · [Bellman-Ford →](bellman_ford.md)
