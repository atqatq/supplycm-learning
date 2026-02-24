---
title: "DFS Traversal | supplycm Algorithm Library"
description: "Plain-English explanation of dfs_traversal from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, dfs_traversal, supply chain, plain english, networks"
---

# DFS Traversal

> **Call it:** `from supplycm.network import dfs_traversal` · **Level:** Beginner · **You need:** basic arithmetic only

Depth-first search dives deep: follow one path as far as it goes, backtrack, try the next. It visits EVERY node reachable from the start - the order is quirky, but completeness is guaranteed. It is the foundation for many clever graph algorithms.

**Think of it like this:** Exploring a cave system with one rope: follow each tunnel to its dead end, rewind, try the next - you will map every chamber.

## When to reach for it

- Enumerating everything reachable (is the customer reachable from this node?)
- The building block behind cycle, bridge, and component detection

## Try it with supplycm

```python
from supplycm.network import dfs_traversal

result = dfs_traversal(graph={0: [1, 2], 1: [0, 3], 2: [0], 3: [1]}, start=0)
print(result)
```

You should see something like:

```text
[0, 1, 3, 2]
```

The visit order dives deep first (0, 1, 3, then backtracks to 2) - not shortest paths, but complete coverage.

## Check yourself

1. DFS vs BFS in one line each?
2. What is DFS bad at?
3. Why do so many algorithms build on DFS?

<details>
<summary>Show answers</summary>

1. DFS dives deep then backtracks; BFS sweeps level by level - deep vs wide.

2. Shortest paths in unweighted graphs - it happily reports long routes discovered first.

3. Its backtrack structure naturally exposes cycles, bridges, and components - the graph's skeleton.

</details>

## Try this now

Trace DFS by hand on a small graph with a cycle; mark where backtracking happens and what it proves.

---
[← BFS Shortest Path](bfs_shortest_path.md) · [Back to Networks library](README.md) · [Bidirectional Search →](bidirectional_search.md)
