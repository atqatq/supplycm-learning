---
title: "Eigenvector Centrality | supplycm Algorithm Library"
description: "Plain-English explanation of eigenvector_centrality from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, eigenvector_centrality, supply chain, plain english, networks"
---

# Eigenvector Centrality

> **Call it:** `from supplycm.network import eigenvector_centrality` · **Level:** Advanced · **You need:** basic arithmetic only

Status by association: you're important if YOUR neighbors are important. A node linked to three hubs outranks one linked to thirty nobodies. The scores feed on each other - a node's value flows from its circle's value, computed to stability.

**Think of it like this:** Reputation: being vouched for by three respected elders outweighs a hundred nods from strangers - importance is contagious.

## When to reach for it

- Identifying influence in supplier/customer networks
- Scoring nodes whose value depends on WHO they connect to

## Try it with supplycm

```python
from supplycm.network import eigenvector_centrality

result = eigenvector_centrality(graph={0: [1, 2], 1: [0, 3], 2: [0], 3: [1]}, nodes=[0, 1, 2, 3])
print(result)
```

You should see something like:

```text
{0: 0.6015, 1: 0.6015, 2: 0.3717, 3: 0.3717}
```

Scores per node - the well-connected pair leads, and even its neighbors inherit elevated scores: importance ripples outward.

## Check yourself

1. How does this differ from degree centrality?
2. Why do scores depend on each other?
3. In supply terms, who is eigenvector-central?

<details>
<summary>Show answers</summary>

1. Quality over quantity - connections to important nodes count more than connections to periphery.

2. That's the definition: my score is built from my neighbors' scores - the math solves them all simultaneously.

3. Suppliers of suppliers - you may not trade with them directly, but their health propagates through your network.

</details>

## Try this now

Add one link from a leaf to the top hub; watch how the leaf's score rises just by touching importance.

---
[← Betweenness Centrality](betweenness_centrality.md) · [Back to Networks library](README.md) · [PageRank →](page_rank.md)
