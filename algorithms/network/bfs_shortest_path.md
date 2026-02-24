---
title: "BFS Shortest Path | supplycm Algorithm Library"
description: "Plain-English explanation of bfs_shortest_path from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, bfs_shortest_path, supply chain, plain english, networks"
---

# BFS Shortest Path

> **Call it:** `from supplycm.network import bfs_shortest_path` · **Level:** Beginner · **You need:** basic arithmetic only

Breadth-first search explores a network in rings: all direct neighbors, then neighbors-of-neighbors. The first time it reaches the target, it has found a path with the FEWEST steps - perfect when every hop costs the same (every link is a road, not a toll road).

**Think of it like this:** Ripples in a pond: drop a stone at your start and watch the wave reach your friend - the ripple's path is the fewest-jumps route.

## When to reach for it

- Fewest-hops questions: connection chains, referral paths
- Unweighted networks (same cost per link)

## Try it with supplycm

```python
from supplycm.network import bfs_shortest_path

result = bfs_shortest_path(graph={0: [1, 2], 1: [0, 3], 2: [0], 3: [1]}, source=0, target=3)
print(result)
```

You should see something like:

```text
[0, 1, 3]
```

The path [0, 1, 3] - two hops, the fewest possible; BFS checked the whole first ring before venturing deeper.

## Check yourself

1. When is BFS the right shortest-path tool?
2. What does BFS guarantee that DFS doesn't?
3. Why 'breadth' first?

<details>
<summary>Show answers</summary>

1. When all links cost the same - then fewest hops equals cheapest path.

2. Shortest (fewest-edge) paths in unweighted graphs - DFS wanders and may find long paths first.

3. It expands the whole frontier level by level, like ripples - hence breadth, not depth.

</details>

## Try this now

Draw a 6-node network with two competing routes; run BFS and verify it always returns the fewer-hop one.

---
[Back to Networks library](README.md) · [DFS Traversal →](dfs_traversal.md)

*New to this topic? Start with the core lesson first: [06_transportation.md](../../modules/06_transportation.md).*
