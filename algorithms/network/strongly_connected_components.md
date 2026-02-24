---
title: "Strongly Connected Components | supplycm Algorithm Library"
description: "Plain-English explanation of strongly_connected_components from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, strongly_connected_components, supply chain, plain english, networks"
---

# Strongly Connected Components

> **Call it:** `from supplycm.network import strongly_connected_components` · **Level:** Advanced · **You need:** basic arithmetic only

For DIRECTED networks: groups where every node can reach every OTHER node in the group - and get back. One-way streets break groups apart even when weak connectivity holds. SCCs reveal the true 'clubs' inside one-way flow networks.

**Think of it like this:** Mutual acquaintances: everyone in the group can reach everyone else AND be reached back - one-way admiration doesn't count.

## When to reach for it

- One-way supply or process networks
- Finding node clusters with guaranteed round-trip flow

## Try it with supplycm

```python
from supplycm.network import strongly_connected_components

result = strongly_connected_components(graph={0: [1], 1: [2], 2: [0]})
print(result)
```

You should see something like:

```text
[[2, 1, 0]]
```

The component list - here one SCC: all three nodes cycle back to each other; reverse an arrow and the club splinters.

## Check yourself

1. Why does direction split weakly-connected groups?
2. What's an SCC of size 1 telling you?
3. Where do SCCs matter in supply chains?

<details>
<summary>Show answers</summary>

1. Because reaching OUT is not reaching BACK - one-way links fail the mutual test.

2. That node cannot return to itself - a dead-end or pure source in the flow structure.

3. Return loops: reverse logistics and closed-loop cycles need genuine mutual reachability to function.

</details>

## Try this now

Flip one edge in a 4-node cycle and watch the SCC structure collapse; name which round trips died.

---
[← Connected Components](connected_components.md) · [Back to Networks library](README.md) · [Maximal Clique (Bron-Kerbosch) →](maximal_clique_bron_kerbosch.md)
