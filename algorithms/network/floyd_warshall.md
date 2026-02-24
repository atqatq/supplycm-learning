---
title: "Floyd-Warshall | supplycm Algorithm Library"
description: "Plain-English explanation of floyd_warshall from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, floyd_warshall, supply chain, plain english, networks"
---

# Floyd-Warshall

> **Call it:** `from supplycm.network import floyd_warshall` · **Level:** Advanced · **You need:** basic arithmetic only

The elegant all-pairs algorithm: consider each node in turn as a possible stopover, and whenever going THROUGH it is cheaper, update the table. Three nested loops later, the complete distance matrix is done - famously short code, famously useful output.

**Think of it like this:** Testing every city as a layover: 'is Paris-to-Rome cheaper via Zurich?' - check every via, and the whole fare chart optimizes itself.

## When to reach for it

- Dense distance matrices over modest node counts
- Teaching dynamic programming with a visible payoff

## Try it with supplycm

```python
from supplycm.network import floyd_warshall

result = floyd_warshall(distances=[[0, 4, 1], [99, 0, 2], [99, 99, 0]])
print(result)
```

You should see something like:

```text
[[0, 4, 1], [99, 0, 2], [99, 99, 0]]
```

The updated matrix - entries that shrank found a cheaper stopover; entries still at 99 are genuinely unreachable.

## Check yourself

1. What is the algorithm's one idea?
2. When is Floyd-Warshall preferable to repeated Dijkstra?
3. How would you detect negative cycles with it?

<details>
<summary>Show answers</summary>

1. For each possible stopover k, test whether i-to-k-to-j beats i-to-j - repeat for all k and optimality falls out.

2. Dense graphs and small-to-medium n - its simplicity wins; for sparse graphs, repeated Dijkstra usually wins.

3. A diagonal entry turning negative - the node found a profitable loop through itself.

</details>

## Try this now

Add a 'via' node connecting two expensive lanes and watch two matrix entries shrink after one k iteration.

---
[← All-Pairs Shortest Path](all_pairs_shortest_path.md) · [Back to Networks library](README.md) · [Connected Components →](connected_components.md)
