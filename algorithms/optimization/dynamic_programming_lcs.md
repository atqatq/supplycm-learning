---
title: "Longest Common Subsequence | supplycm Algorithm Library"
description: "Plain-English explanation of dynamic_programming_lcs from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, dynamic_programming_lcs, supply chain, plain english, optimization"
---

# Longest Common Subsequence

> **Call it:** `from supplycm.optimization import dynamic_programming_lcs` · **Level:** Advanced · **You need:** basic arithmetic only

The longest pattern two sequences SHARE in order (gaps allowed): 'ABCBDAB' and 'BDCABA' share 'BDAB'. The workhorse behind file diffs, DNA comparison, and 'how similar are these two lists really?' questions.

**Think of it like this:** Comparing two route plans stop by stop: the stops they agree on, in order - ignoring the detours each took - form the common core.

## When to reach for it

- Comparing plans, routes, or process steps for shared structure
- The general 'similarity in order' score behind diff tools

## Try it with supplycm

```python
from supplycm.optimization import dynamic_programming_lcs

result = dynamic_programming_lcs(s1=list('ABCBDAB'), s2=list('BDCABA'))
print(result)
```

You should see something like:

```text
['B', 'D', 'A', 'B']
```

The shared core ['B', 'D', 'A', 'B'] - four symbols the sequences agree on in order; everything else was divergence.

## Check yourself

1. LCS vs edit distance - how do they relate?
2. Why allow gaps in the match?
3. Where would you use this in supply chains?

<details>
<summary>Show answers</summary>

1. Two lenses on similarity: LCS counts agreement; edit distance counts corrections needed - one long LCS means small distance.

2. Real sequences drift - plans take different detours but keep the same backbone; gaps forgive the drift while honoring order.

3. Comparing two planners' route sequences or standard vs actual process steps - the shared core shows what both agree happened.

</details>

## Try this now

Compute the LCS of two variant pick-routes (same 8 stops, different order); discuss what the shared core means.

---
[← Longest Increasing Subsequence](longest_increasing_subsequence.md) · [Back to Optimization library](README.md) · [Matrix Chain Multiplication →](matrix_chain_multiplication.md)
