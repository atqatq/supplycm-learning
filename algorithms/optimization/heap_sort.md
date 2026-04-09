---
title: "Heap Sort | supplycm Algorithm Library"
description: "Plain-English explanation of heap_sort from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, heap_sort, supply chain, plain english, optimization"
---

# Heap Sort

> **Call it:** `from supplycm.optimization import heap_sort` · **Level:** Intermediate · **You need:** basic arithmetic only

Sort by tournament: arrange items in a 'heap' where the biggest always sits on top, repeatedly pluck the winner, and rebuild. Guaranteed fast on ANY input - no lucky or unlucky orders. The reliable workhorse when worst-case promises matter.

**Think of it like this:** A single-elimination tournament: the champion surfaces quickly, remove them, rerun the affected matches - the next champion emerges almost free.

## When to reach for it

- Guaranteed-speed sorting where predictability matters
- Understanding priority queues - the machinery behind schedulers

## Try it with supplycm

```python
from supplycm.optimization import heap_sort

result = heap_sort(arr=[5, 2, 9, 1, 7])
print(result)
```

You should see something like:

```text
[1, 2, 5, 7, 9]
```

The sorted list - built by repeatedly extracting the current maximum from the heap structure.

## Check yourself

1. What does the 'heap' guarantee?
2. Why choose heap sort over quicksort?
3. Where do heaps secretly run your day?

<details>
<summary>Show answers</summary>

1. The largest element is always instantly accessible at the top - finding it costs nothing, removing costs little.

2. Its worst case is solid: quicksort can degrade badly on adversarial input; heap sort never does.

3. Operating system schedulers, event queues, Dijkstra's algorithm - anywhere 'next most urgent, please' is asked constantly.

</details>

## Try this now

Sort 8 numbers by hand drawing the heap after each extraction; feel why the next winner comes cheaply.

---
[← Binary Search](binary_search.md) · [Back to Optimization library](README.md) · [Merge Sort →](merge_sort.md)
