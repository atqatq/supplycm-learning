---
title: "Betweenness Centrality | supplycm Algorithm Library"
description: "Plain-English explanation of betweenness_centrality from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, betweenness_centrality, supply chain, plain english, networks"
---

# Betweenness Centrality

> **Call it:** `from supplycm.network import betweenness_centrality` · **Level:** Intermediate · **You need:** basic arithmetic only

Betweenness counts how often a node sits ON THE SHORT PATH between others - the gatekeeper score. High-betweenness nodes may have few links but control the flow between regions. Remove them and distances explode even if the network stays connected.

**Think of it like this:** The one bilingual employee between two offices: not the most connected person - but nothing moves between floors without passing through them.

## When to reach for it

- Finding chokepoints that aren't obvious hubs
- Understanding where flow congestion or failure concentrates

## Try it with supplycm

```python
from supplycm.network import betweenness_centrality

result = betweenness_centrality(graph={0: [1, 2], 1: [0, 3], 2: [0], 3: [1]}, nodes=[0, 1, 2, 3])
print(result)
```

You should see something like:

```text
{0: 2.0, 1: 2.0, 2: 0.0, 3: 0.0}
```

Scores per node - 0 and 1 gatekeep all traffic between the {2} side and the {3} side; the leaves score zero despite being essential endpoints.

## Check yourself

1. High degree vs high betweenness - when do they disagree?
2. What happens to a network when a top-betweenness node fails?
3. How would you reduce dangerous betweenness?

<details>
<summary>Show answers</summary>

1. Bridge nodes: few links, all of them essential - low degree, high betweenness.

2. Paths lengthen or break between whole regions - connectivity degrades disproportionately.

3. Add a bypass lane or second gatekeeper - split the gatekeeping, share the risk.

</details>

## Try this now

Compute betweenness before and after adding one bypass edge; watch the gatekeeper's score and your risk fall together.

---
[← Closeness Centrality](closeness_centrality.md) · [Back to Networks library](README.md) · [Eigenvector Centrality →](eigenvector_centrality.md)
