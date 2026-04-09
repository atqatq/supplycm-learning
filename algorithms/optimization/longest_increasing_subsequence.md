---
title: "Longest Increasing Subsequence | supplycm Algorithm Library"
description: "Plain-English explanation of longest_increasing_subsequence from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, longest_increasing_subsequence, supply chain, plain english, optimization"
---

# Longest Increasing Subsequence

> **Call it:** `from supplycm.optimization import longest_increasing_subsequence` · **Level:** Advanced · **You need:** basic arithmetic only

The longest run (not necessarily adjacent) of values that keep rising through a sequence. In [10, 9, 2, 5, 3, 7, 101, 18] it's 2, 5, 7, 101 - length 4. A quiet classic that models 'the longest improving streak' hiding inside noisy data.

**Think of it like this:** Picking the longest chain of personal records from a messy training log: some weeks dip, but the RECORD-beating moments form their own rising line.

## When to reach for it

- Finding improving trends buried in noisy series
- Classic DP training with real pattern-hunting instincts

## Try it with supplycm

```python
from supplycm.optimization import longest_increasing_subsequence

result = longest_increasing_subsequence([10, 9, 2, 5, 3, 7, 101, 18])
print(result)
```

You should see something like:

```text
4
```

Length 4 - one rising thread survives the noise; the dips were skips, not breaks, in the best chain.

## Check yourself

1. Why 'subsequence' rather than 'substring'?
2. What would this reveal on weekly demand?
3. Why is brute force painful here?

<details>
<summary>Show answers</summary>

1. Elements need not sit adjacent - the chain can skip noise, which is exactly what makes it robust to dips.

2. The strongest sustained growth thread - weeks that kept outdoing earlier weeks, ignoring the noise between.

3. Every subset and order combination is a candidate - DP instead asks 'best chain ENDING at each item' and chains forward.

</details>

## Try this now

Find the LIS of monthly sales with two dips; mark the four rising months and verify the function agrees.

---
[← Edit Distance](edit_distance.md) · [Back to Optimization library](README.md) · [Longest Common Subsequence →](dynamic_programming_lcs.md)
