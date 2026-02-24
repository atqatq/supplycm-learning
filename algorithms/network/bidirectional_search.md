---
title: "Bidirectional Search | supplycm Algorithm Library"
description: "Plain-English explanation of bidirectional_search from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, bidirectional_search, supply chain, plain english, networks"
---

# Bidirectional Search

> **Call it:** `from supplycm.network import bidirectional_search` · **Level:** Intermediate · **You need:** basic arithmetic only

Search from BOTH ends at once: BFS forward from the start and backward from the target, until the waves meet in the middle. Explored area shrinks dramatically - the classic trick that turns an impossible search into an instant one.

**Think of it like this:** Two search parties, one from each trailhead, meeting at the lake - together they cover half the park each.

## When to reach for it

- Huge graphs where one-directional BFS is too slow
- Route queries on networks with known endpoints

## Try it with supplycm

```python
from supplycm.network import bidirectional_search

result = bidirectional_search(graph={0: [1, 2], 1: [0, 3], 2: [0], 3: [1]}, source=0, target=3)
print(result)
```

You should see something like:

```text
[0, 1, 3]
```

A meeting-point path - both searches expanded small rings instead of one giant wave, and the handshake happened quickly.

## Check yourself

1. Why is bidirectional search dramatically faster?
2. What does it need to work?
3. When does the trick fail?

<details>
<summary>Show answers</summary>

1. Each side explores a ring whose size grows exponentially - two half-depth rings are far smaller than one full-depth ring.

2. A clear target to search backward from, and edges you can legally traverse in reverse.

3. Directed networks where reverse edges are invalid, or when the target is vague rather than specific.

</details>

## Try this now

On a 5-deep chain graph, count nodes visited by one-way BFS vs bidirectional - feel the speedup numerically.

---
[← DFS Traversal](dfs_traversal.md) · [Back to Networks library](README.md) · [Dijkstra's Shortest Path →](dijkstra_shortest_path.md)
