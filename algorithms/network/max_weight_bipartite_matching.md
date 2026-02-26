---
title: "Max-Weight Bipartite Matching | supplycm Algorithm Library"
description: "Plain-English explanation of max_weight_bipartite_matching from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, max_weight_bipartite_matching, supply chain, plain english, networks"
---

# Max-Weight Bipartite Matching

> **Call it:** `from supplycm.network import max_weight_bipartite_matching` · **Level:** Advanced · **You need:** basic arithmetic only

Matching with opinions: every possible pairing has a value, and you want the set of pairings with the HIGHEST TOTAL. Not just any assignment - the best assignment. This is the math behind optimal driver-load dispatch and optimal worker-task assignment.

**Think of it like this:** The dance organizer now scores every possible pair by chemistry and picks the lineup with the most total spark - not the most pairs, the most value.

## When to reach for it

- Optimal dispatch: drivers to loads, techs to jobs
- Any assignment where quality differences between pairings matter

## Try it with supplycm

```python
from supplycm.network import max_weight_bipartite_matching

result = max_weight_bipartite_matching(weight_matrix=[[3, 1], [2, 4]])
print(result)
```

You should see something like:

```text
[[[0, 0], [1, 1]], 7.0]
```

The chosen pairs and total value 7 - note it skipped the tempting 3+2 pairing for 3+4; totals beat singles.

## Check yourself

1. Matching count vs matching value - what's the difference?
2. What does the weight represent in dispatch?
3. Why can't greedy 'best pair first' solve it?

<details>
<summary>Show answers</summary>

1. Weighted versions trade pair COUNT for pair QUALITY - sometimes fewer, better pairs win outright.

2. Profit, priority, or fit score per pairing - the matrix is your business judgment in numbers.

3. Early best-pairs can block later great pairs - the optimal set sometimes sacrifices a good single for a great combo.

</details>

## Try this now

Nudge one weight and flip the optimal pairing; find the smallest change that reverses the decision.

---
[← Bipartite Matching](bipartite_matching.md) · [Back to Networks library](README.md) · [Min-Weight Bipartite Matching →](min_weight_bipartite_matching.md)
