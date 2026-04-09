---
title: "Merge Sort | supplycm Algorithm Library"
description: "Plain-English explanation of merge_sort from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, merge_sort, supply chain, plain english, optimization"
---

# Merge Sort

> **Call it:** `from supplycm.optimization import merge_sort` · **Level:** Intermediate · **You need:** basic arithmetic only

Divide and conquer refined: split the list in half, sort each half, then ZIP the sorted halves together with a merge pass. Predictably excellent, and the natural algorithm when data doesn't fit in memory - halves can live on different disks.

**Think of it like this:** Merging two sorted stacks of exam papers: compare the top sheets, place the lower, repeat - a perfectly ordered pile emerges without re-scanning everything.

## When to reach for it

- Sorting large or external datasets
- Stable sorting where equal items keep their order

## Try it with supplycm

```python
from supplycm.optimization import merge_sort

result = merge_sort(arr=[5, 2, 9, 1, 7])
print(result)
```

You should see something like:

```text
[1, 2, 5, 7, 9]
```

The sorted list - produced by halving, halving, then merging upward; the merge steps do all the actual deciding.

## Check yourself

1. Why is merging two SORTED lists cheap?
2. What does 'stable' mean and why care?
3. When would you pick merge over quicksort?

<details>
<summary>Show answers</summary>

1. One pass with top-of-each comparisons - no element is ever revisited; that's the entire efficiency story.

2. Equal items keep their original relative order - crucial when sorting by one column after another.

3. When worst-case guarantees, stability, or external memory matter - otherwise quicksort's speed usually wins.

</details>

## Try this now

Merge [1, 4, 7] with [2, 3, 9] by hand in one pass; count comparisons and see the no-rescan promise.

---
[← Heap Sort](heap_sort.md) · [Back to Optimization library](README.md) · [Quick Sort →](quick_sort.md)
