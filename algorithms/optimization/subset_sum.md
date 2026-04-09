---
title: "Subset Sum | supplycm Algorithm Library"
description: "Plain-English explanation of subset_sum from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, subset_sum, supply chain, plain english, optimization"
---

# Subset Sum

> **Call it:** `from supplycm.optimization import subset_sum` · **Level:** Intermediate · **You need:** basic arithmetic only

Is there a subset of these numbers that adds up EXACTLY to the target? Deceptively simple, famously hard in general - and solvable by dynamic programming when numbers are reasonable. The purest 'exact combination exists?' question.

**Think of it like this:** Paying exactly 9 dollars from coins {3, 34, 4, 12, 5, 2}: can some handful hit it precisely? Try 3+4+2.

## When to reach for it

- Exact-fill questions: order quantities, packaging, batching
- Understanding why 'exact' versions of easy questions turn hard

## Try it with supplycm

```python
from supplycm.optimization import subset_sum

result = subset_sum(nums=[3, 34, 4, 12, 5, 2], target=9)
print(result)
```

You should see something like:

```text
True
```

True - 3 + 4 + 2 hits 9 exactly; change the target to 10 and watch the answer flip after real searching.

## Check yourself

1. Why is subset sum hard when summing is trivial?
2. How does DP tame it for moderate numbers?
3. Where does exact-fill matter in supply chains?

<details>
<summary>Show answers</summary>

1. The number of SUBSETS grows explosively - 2^n candidates; the question is whether an exact needle hides in that haystack.

2. It records which totals are reachable so far - reachability spreads forward, skipping impossible branches entirely.

3. Cutting stock, truck cube-out, batch formulation - 'can these orders combine into one full load?' is subset sum in work clothes.

</details>

## Try this now

Test targets 9 through 13 on the same numbers; list which are achievable and trace one combination each.

---
[← 0-1 Knapsack (Dynamic Programming)](knapsack_01_dp.md) · [Back to Optimization library](README.md) · [Edit Distance →](edit_distance.md)
