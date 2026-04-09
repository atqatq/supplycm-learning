---
title: "Binary Search | supplycm Algorithm Library"
description: "Plain-English explanation of binary_search from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, binary_search, supply chain, plain english, optimization"
---

# Binary Search

> **Call it:** `from supplycm.optimization import binary_search` · **Level:** Beginner · **You need:** basic arithmetic only

Find an item in a SORTED list by halving: check the middle, discard half, repeat. Twenty questions find anything in a million items. The most famous efficiency trick in computing - and the spirit behind 'bisect to decide' in everything from search to capacity planning.

**Think of it like this:** Finding a name in a phone book: open the middle, decide left or right, repeat - nobody flips page by page.

## When to reach for it

- Locating items in sorted data instantly
- Any 'yes up to here, no after' boundary hunting

## Try it with supplycm

```python
from supplycm.optimization import binary_search

result = binary_search(arr=[1, 3, 5, 7, 9], target=7)
print(result)
```

You should see something like:

```text
3
```

Index 3 - found in three halvings instead of four scans; the gap grows with list size, and grows fast.

## Check yourself

1. What must be true before binary search works?
2. A million sorted items take how many checks?
3. Where does binary search show up beyond lookup?

<details>
<summary>Show answers</summary>

1. The data must be sorted - order is what lets each comparison discard half.

2. About 20 - each check halves the range; that's logarithmic speed, the whole magic.

3. Capacity search: 'what's the smallest capacity that fits?' - bisect on the answer, exactly like multifit does.

</details>

## Try this now

Search 20 sorted numbers by hand with the halving method; count your checks versus a linear scan.

---
[Back to Optimization library](README.md) · [Heap Sort →](heap_sort.md)
