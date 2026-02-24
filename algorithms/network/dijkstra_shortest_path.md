---
title: "Dijkstra's Shortest Path | supplycm Algorithm Library"
description: "Plain-English explanation of dijkstra_shortest_path from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, dijkstra_shortest_path, supply chain, plain english, networks"
---

# Dijkstra's Shortest Path

> **Call it:** `from supplycm.network import dijkstra_shortest_path` · **Level:** Intermediate · **You need:** basic arithmetic only

The workhorse of weighted routing: from the start, always expand the CHEAPEST known node next, updating neighbors' best distances. It returns the cheapest path costs from the start to every node - the algorithm behind every 'fastest route' you've ever been shown.

**Think of it like this:** Filling a map with flood water from the source: water reaches each city via the cheapest possible route, in order of cost.

## When to reach for it

- Cheapest routes on networks with positive costs (distance, time, money)
- One-origin, many-destinations routing questions

## Try it with supplycm

```python
from supplycm.network import dijkstra_shortest_path

result = dijkstra_shortest_path(graph={0: [(1, 4), (2, 1)], 1: [(3, 1)], 2: [(1, 2), (3, 5)], 3: []}, source=0, target=3)
print(result)
```

You should see something like:

```text
[{0: 0.0, 1: 3.0, 2: 1.0, 3: 4.0}, {1: 2, 2: 0, 3: 1}]
```

Distances to every node plus predecessor hints - node 3 costs 4 via node 1, not 5 direct: the detour through 2 and 1 wins.

## Check yourself

1. What's Dijkstra's golden assumption?
2. Why does it always expand the cheapest frontier node?
3. How does this map to logistics?

<details>
<summary>Show answers</summary>

1. No negative costs - the 'cheapest so far' logic breaks if a later edge could subtract cost.

2. Greedy certainty: once popped, no cheaper route can ever appear - that's the proof's whole trick.

3. Nodes are locations, edges are lanes with cost per shipment - Dijkstra answers 'cheapest way from A to everywhere'.

</details>

## Try this now

Add a tempting-but-expensive direct edge to a network and verify Dijkstra still finds the cheap detour.

---
[← Bidirectional Search](bidirectional_search.md) · [Back to Networks library](README.md) · [A* Search →](a_star_search.md)

*New to this topic? Start with the core lesson first: [06_transportation.md](../../modules/06_transportation.md).*
