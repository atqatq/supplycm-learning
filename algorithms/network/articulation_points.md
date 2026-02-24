---
title: "Articulation Points | supplycm Algorithm Library"
description: "Plain-English explanation of articulation_points from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, articulation_points, supply chain, plain english, networks"
---

# Articulation Points

> **Call it:** `from supplycm.network import articulation_points` · **Level:** Advanced · **You need:** basic arithmetic only

Articulation points are the load-bearing nodes: remove one and the network splits into islands. They are your single points of failure - the hubs whose loss fractures connectivity. Risk management starts by naming them.

**Think of it like this:** The one bridge into town: close it for repairs and the town halves - everyone knew the bridge mattered; now it's proven.

## When to reach for it

- Vulnerability audits of distribution or communication networks
- Deciding where redundancy investments pay off most

## Try it with supplycm

```python
from supplycm.network import articulation_points

result = articulation_points(graph={0: [1, 2], 1: [0], 2: [0]})
print(result)
```

You should see something like:

```text
{0}
```

Node 0 is flagged - remove it and nodes 1 and 2 become strangers; every path between them runs through 0.

## Check yourself

1. What does an articulation point mean operationally?
2. How do you fix a critical articulation point?
3. Do hubs always matter this way?

<details>
<summary>Show answers</summary>

1. A node whose failure disconnects others - the network's single points of failure, by definition.

2. Add a bypass edge or node around it - redundancy converts critical into survivable.

3. No - a hub with redundant connections can fail without splitting anything; criticality is about STRUCTURE, not traffic volume.

</details>

## Try this now

Map your (real or invented) network, find its articulation points, and price one bypass edge for the worst one.

---
[← Topological Sort](topological_sort.md) · [Back to Networks library](README.md) · [Bridges in Graph →](bridges_in_graph.md)
