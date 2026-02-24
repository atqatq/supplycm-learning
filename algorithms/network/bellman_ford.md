---
title: "Bellman-Ford | supplycm Algorithm Library"
description: "Plain-English explanation of bellman_ford from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, bellman_ford, supply chain, plain english, networks"
---

# Bellman-Ford

> **Call it:** `from supplycm.network import bellman_ford` · **Level:** Advanced · **You need:** basic arithmetic only

The careful shortest-path algorithm: relax every edge repeatedly, and even NEGATIVE costs are handled correctly. It also detects negative cycles - 'profitable loops' that break shortest-path math entirely. Slower than Dijkstra, but immune to tricks that break it.

**Think of it like this:** A meticulous accountant re-checking every ledger line n-1 times: slow, thorough, and the only one who catches the fraudulent loop.

## When to reach for it

- Networks where costs can be negative (subsidies, credits)
- Detecting arbitrage cycles (currency-style profitable loops)

## Try it with supplycm

```python
from supplycm.network import bellman_ford

result = bellman_ford(graph={0: [(1, 4), (2, 1)], 1: [(3, 1)], 2: [(1, 2), (3, 5)], 3: []}, source=0, num_nodes=4)
print(result)
```

You should see something like:

```text
[{0: 0.0, 1: 3.0, 2: 1.0, 3: 4.0}, False]
```

Distances plus a False flag - no negative cycle exists, so the distances are trustworthy and final.

## Check yourself

1. What can Bellman-Ford do that Dijkstra can't?
2. What does a negative cycle mean in business terms?
3. Why is it slower?

<details>
<summary>Show answers</summary>

1. Survive negative edge costs AND report negative cycles - Dijkstra returns nonsense on both.

2. A profitable loop - ship around it forever and gain endlessly; arbitrage, or a data error worth fixing.

3. It relaxes ALL edges repeatedly without Dijkstra's greedy shortcut - the price of paranoia.

</details>

## Try this now

Create a 3-edge loop whose costs sum to -1; watch the flag flip True and explain the arbitrage reading.

---
[← A* Search](a_star_search.md) · [Back to Networks library](README.md) · [All-Pairs Shortest Path →](all_pairs_shortest_path.md)
