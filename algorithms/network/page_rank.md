---
title: "PageRank | supplycm Algorithm Library"
description: "Plain-English explanation of page_rank from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, page_rank, supply chain, plain english, networks"
---

# PageRank

> **Call it:** `from supplycm.network import page_rank` · **Level:** Advanced · **You need:** basic arithmetic only

The algorithm behind Google, applied to your network: importance flows along edges, distributed across each node's links, with a small damping factor keeping everything honest. Nodes linked FROM important nodes become important - and the math converges to stable scores.

**Think of it like this:** A room where everyone redistributes their attention to the people they follow - after enough rounds, the genuinely influential stay standing in the spotlight.

## When to reach for it

- Scoring influence in multi-tier supply networks
- Any 'who really matters here' ranking with flow semantics

## Try it with supplycm

```python
from supplycm.network import page_rank

result = page_rank(graph={0: [1, 2], 1: [0, 3], 2: [0], 3: [1]}, num_nodes=4, damping=0.85)
print(result)
```

You should see something like:

```text
{0: 0.3246, 1: 0.3246, 2: 0.1754, 3: 0.1754}
```

Scores summing to 1 - the hub pair dominates, but even leaves inherit some importance through their single influential friend.

## Check yourself

1. What does the damping factor represent?
2. PageRank vs eigenvector centrality - family resemblance?
3. Why does splitting attention matter?

<details>
<summary>Show answers</summary>

1. The chance a random surfer jumps anywhere - it stabilizes the math and stops dead-ends from swallowing all the score.

2. Close cousins - PageRank adds damping and outgoing-link splitting; eigenvector is the purer version.

3. A node with many outgoing links passes less to each - endorsing everyone means standing for nothing.

</details>

## Try this now

Raise damping from 0.5 to 0.9 and watch scores concentrate - explain what 'trusting the links more' means.

---
[← Eigenvector Centrality](eigenvector_centrality.md) · [Back to Networks library](README.md) · [Bipartite Matching →](bipartite_matching.md)
