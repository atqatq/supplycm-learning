---
title: "Quick Sort | supplycm Algorithm Library"
description: "Plain-English explanation of quick_sort from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, quick_sort, supply chain, plain english, optimization"
---

# Quick Sort

> **Call it:** `from supplycm.optimization import quick_sort` · **Level:** Intermediate · **You need:** basic arithmetic only

Pick a pivot, split items into smaller and larger, sort the two sides, repeat. Usually the fastest general sort in practice - its constant factors are tiny - though its worst case is famously bad on adversarial inputs. The speed demon with an asterisk.

**Think of it like this:** Organizing people at a networking event by height: pick a reference person, shorter left, taller right, and repeat within each group - the crowd sorts itself in waves.

## When to reach for it

- General in-memory sorting where average speed wins
- The default choice in most language standard libraries

## Try it with supplycm

```python
from supplycm.optimization import quick_sort

result = quick_sort(arr=[5, 2, 9, 1, 7])
print(result)
```

You should see something like:

```text
[1, 2, 5, 7, 9]
```

The sorted list - each pivot split the problem, and the recursion did the rest; average behavior is superb.

## Check yourself

1. What's quicksort's dirty secret?
2. How do real libraries tame the worst case?
3. Quicksort vs merge sort - one-line trade-off?

<details>
<summary>Show answers</summary>

1. Its worst case - sorted or adversarial pivots can collapse it toward slow, quadratic behavior.

2. Random pivots, median-of-three, or hybrid fallbacks (introsort switches to heap sort when recursion misbehaves).

3. Speed vs guarantees: quicksort wins on average; merge sort wins on certainty and stability.

</details>

## Try this now

Sort [3, 1, 4, 1, 5, 9, 2, 6] by hand choosing first-element pivots; note where the split was lopsided.

---
[← Merge Sort](merge_sort.md) · [Back to Optimization library](README.md) · [Fractional Knapsack →](fractional_knapsack.md)
