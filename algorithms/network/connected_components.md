---
title: "Connected Components | supplycm Algorithm Library"
description: "Plain-English explanation of connected_components from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, connected_components, supply chain, plain english, networks"
---

# Connected Components

> **Call it:** `from supplycm.network import connected_components` · **Level:** Beginner · **You need:** basic arithmetic only

Which nodes can reach which? Components group the network into islands of mutual reachability. In supply terms: separate clusters that no shared lane connects. One call, and the network's geography is understood.

**Think of it like this:** Archipelago mapping: which islands can you hop between, and which require a plane (or are unreachable)?

## When to reach for it

- Checking network cohesion after disruptions
- Finding isolated customers, warehouses, or suppliers

## Try it with supplycm

```python
from supplycm.network import connected_components

result = connected_components(graph={0: [1], 1: [0], 2: [3], 3: [2], 4: []})
print(result)
```

You should see something like:

```text
[[0, 1], [2, 3], [4]]
```

Islands return as lists - {0,1}, {2,3}, and lonely node 4; three separate worlds in one network.

## Check yourself

1. What does it mean if everything is one component?
2. A key supplier's node forms its own island after an edge fails - now what?
3. How is this different from strongly connected components?

<details>
<summary>Show answers</summary>

1. Full cohesion - every node reaches every other; no structural isolation.

2. You've found a broken link to repair - or an exposure that needs a backup lane.

3. Weak components ignore direction (any path); strong components demand round-trips - much stricter.

</details>

## Try this now

Remove one edge from a connected network and watch it split into two islands - that edge was a bridge.

---
[← Floyd-Warshall](floyd_warshall.md) · [Back to Networks library](README.md) · [Strongly Connected Components →](strongly_connected_components.md)
