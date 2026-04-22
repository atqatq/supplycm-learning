---
title: "Bin Packing: Best Fit | supplycm Algorithm Library"
description: "Plain-English explanation of bin_packing_best_fit from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, bin_packing_best_fit, supply chain, plain english, optimization"
---

# Bin Packing: Best Fit

> **Call it:** `from supplycm.optimization import bin_packing_best_fit` · **Level:** Intermediate · **You need:** basic arithmetic only

First fit's tidy sibling: place each item into the bin it fits MOST SNUGLY - the smallest remaining space that still holds it - preserving big gaps for future big items. Same speed class, usually slightly smarter fragments.

**Think of it like this:** Parking cars in a lot: put each car in the spot it fits most exactly - never burn a large-space slot on a compact when a tight one exists.

## When to reach for it

- Packing where fragment sizes matter downstream
- Improving on first fit at identical cost

## Try it with supplycm

```python
from supplycm.optimization import bin_packing_best_fit

result = bin_packing_best_fit(items=[4, 8, 1, 4, 2, 1], bin_capacity=10)
print(result)
```

You should see something like:

```text
[[4, 4, 2], [8, 1, 1]]
```

Bins as lists - compare with first-fit's answer; the snug choices left different fragments and sometimes fewer bins.

## Check yourself

1. What does 'best fit' optimize per placement?
2. When does best fit beat first fit, and when not?
3. What's the fundamental limit of all online packing?

<details>
<summary>Show answers</summary>

1. Leftover space minimized - big gaps stay available for big arrivals instead of absorbing small items greedily.

2. Instance-dependent - both are heuristics; the decreasing variant below usually beats both.

3. No lookahead - arrivals are committed as they come; the real gain comes from sorting, i.e., seeing the future.

</details>

## Try this now

Run all three bin-packing variants on the same list; rank them and explain what sorting bought the winner.

---
[← Bin Packing: First Fit](bin_packing_first_fit.md) · [Back to Optimization library](README.md) · [Bin Packing: First Fit Decreasing (FFD) →](bin_packing_first_fit_decreasing.md)
