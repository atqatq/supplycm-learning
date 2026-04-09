---
title: "Edit Distance | supplycm Algorithm Library"
description: "Plain-English explanation of edit_distance from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, edit_distance, supply chain, plain english, optimization"
---

# Edit Distance

> **Call it:** `from supplycm.optimization import edit_distance` · **Level:** Intermediate · **You need:** basic arithmetic only

How many single-letter edits (insert, delete, replace) turn one word into another? 'kitten' to 'sitting' takes 3. Dynamic programming fills a small grid and the answer falls out - the standard similarity score for text, codes, and addresses.

**Think of it like this:** Counting the minimum keystrokes to fix one word into another - each typo fixed cheaply, each reworded phrase costing a few.

## When to reach for it

- Fuzzy matching: addresses, SKUs, customer names
- Data cleaning: catching near-duplicate records

## Try it with supplycm

```python
from supplycm.optimization import edit_distance

result = edit_distance(s1=list('kitten'), s2=list('sitting'))
print(result)
```

You should see something like:

```text
3
```

Distance 3 - substitute k->s, e->i, insert g; any record pair this close deserves a duplicate check.

## Check yourself

1. Why is edit distance better than exact matching for addresses?
2. What does a distance of 1 vs 4 suggest operationally?
3. How does DP build the answer?

<details>
<summary>Show answers</summary>

1. Typos happen - 'Main St' vs 'Main Street' vs 'Maine St' need graded similarity, not binary mismatch.

2. 1: likely the same record with a typo; 4: possibly different entities - thresholds turn distance into decisions.

3. A grid where each cell is the cheapest edit path to that prefix pair - one small comparison per cell, no brute force.

</details>

## Try this now

Compute the distance between 'warehouse' and 'warehous' by hand (answer: 1), then between 'ship' and 'shipping'.

---
[← Subset Sum](subset_sum.md) · [Back to Optimization library](README.md) · [Longest Increasing Subsequence →](longest_increasing_subsequence.md)
