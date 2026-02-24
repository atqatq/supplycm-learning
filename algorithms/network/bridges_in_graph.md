---
title: "Bridges in Graph | supplycm Algorithm Library"
description: "Plain-English explanation of bridges_in_graph from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, bridges_in_graph, supply chain, plain english, networks"
---

# Bridges in Graph

> **Call it:** `from supplycm.network import bridges_in_graph` · **Level:** Advanced · **You need:** basic arithmetic only

Bridges are the load-bearing EDGES: cut one and the network splits. Where articulation points are fragile NODES, bridges are fragile LANES - the single roads, sole shipping lanes, and unique data links whose loss isolates whole regions.

**Think of it like this:** The only railway line into a valley: one landslide and the valley is cut off - everything else could burn and trains would still run.

## When to reach for it

- Lane-level vulnerability audits
- Prioritizing which links get secondary routes

## Try it with supplycm

```python
from supplycm.network import bridges_in_graph

result = bridges_in_graph(graph={0: [1, 2], 1: [0], 2: [0]})
print(result)
```

You should see something like:

```text
[[0, 1], [0, 2]]
```

Both edges (0,1) and (0,2) are bridges - cut either and an entire node drops off the network.

## Check yourself

1. Node-critical vs edge-critical - how do they differ?
2. A busy edge that's NOT a bridge - why is that reassuring?
3. How do you eliminate all bridges?

<details>
<summary>Show answers</summary>

1. Articulation points fail as NODES; bridges fail as LINKS - networks often have different ones of each.

2. Traffic would reroute - the network survives its loss; busy is not the same as critical.

3. Add parallel or alternative edges until every link sits on a cycle - redundancy by construction.

</details>

## Try this now

Add one bypass edge to the example and verify the bridge list shrinks - redundancy, demonstrated.

---
[← Articulation Points](articulation_points.md) · [Back to Networks library](README.md) · [Degree Centrality →](degree_centrality.md)
