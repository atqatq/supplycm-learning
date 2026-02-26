---
title: "Bipartite Matching | supplycm Algorithm Library"
description: "Plain-English explanation of bipartite_matching from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, bipartite_matching, supply chain, plain english, networks"
---

# Bipartite Matching

> **Call it:** `from supplycm.network import bipartite_matching` · **Level:** Intermediate · **You need:** basic arithmetic only

Two groups, one set of allowed pairings: drivers and loads, nurses and shifts, tasks and machines. Matching pairs up as many as possible so nobody is double-booked. The result: the maximum number of feasible pairings, each node used at most once.

**Think of it like this:** A dance organizer pairing callers and dancers by compatibility - maximize happy pairs, nobody dances twice at once.

## When to reach for it

- Assignment feasibility: workers to shifts, trucks to loads
- Any 'who can do what' pairing maximization

## Try it with supplycm

```python
from supplycm.network import bipartite_matching

result = bipartite_matching(graph={0: [2, 3], 1: [2]}, left_nodes=[0, 1])
print(result)
```

You should see something like:

```text
{0: 3, 1: 2}
```

The matched pairs - both left nodes get partners where possible; someone may go unmatched when capacities conflict.

## Check yourself

1. What makes a matching valid?
2. Why can greedy pairing fail?
3. What does an unmatched left node mean operationally?

<details>
<summary>Show answers</summary>

1. Each node appears at most once - no driver takes two loads, no load rides two trucks.

2. A greedy first pick can steal a partner someone else desperately needs - real matching algorithms 'undo' earlier choices.

3. Unmet demand - either add capacity (more right nodes) or loosen compatibility edges.

</details>

## Try this now

Add a third left node that can only use partner 2; verify who goes unmatched and propose the minimal fix.

---
[← PageRank](page_rank.md) · [Back to Networks library](README.md) · [Max-Weight Bipartite Matching →](max_weight_bipartite_matching.md)
