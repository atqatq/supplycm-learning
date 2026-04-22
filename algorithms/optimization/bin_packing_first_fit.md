---
title: "Bin Packing: First Fit | supplycm Algorithm Library"
description: "Plain-English explanation of bin_packing_first_fit from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, bin_packing_first_fit, supply chain, plain english, optimization"
---

# Bin Packing: First Fit

> **Call it:** `from supplycm.optimization import bin_packing_first_fit` · **Level:** Intermediate · **You need:** basic arithmetic only

Pack items into the fewest capacity-limited bins: place each item into the FIRST bin with room, open a new bin only when nothing fits. Instant, intuitive, decent - the daily habit of loaders, with known slack that smarter variants recover.

**Think of it like this:** Loading boxes into moving vans as they arrive: first van with floor space gets each box - nobody plans, yet everything ships.

## When to reach for it

- Pallet, container, and truck loading in order of arrival
- A baseline for comparing packing improvements

## Try it with supplycm

```python
from supplycm.optimization import bin_packing_first_fit

result = bin_packing_first_fit(items=[4, 8, 1, 4, 2, 1], bin_capacity=10)
print(result)
```

You should see something like:

```text
[[4, 1, 4, 1], [8, 2]]
```

Bins as lists - the 8 forced an early second bin that smaller items then filled; order changed everything.

## Check yourself

1. Why can arrival ORDER waste bins?
2. First fit vs best fit - the precise difference?
3. What's the lower bound no algorithm can beat?

<details>
<summary>Show answers</summary>

1. A big early item fragments space - first-fit can't save room for the big one still in the queue.

2. First: the earliest bin with room; best: the TIGHTEST fit - best fit leaves big fragments open for future big items.

3. Total size divided by capacity, rounded up - every packing needs at least that many bins.

</details>

## Try this now

Pack the same items in two different orders with first-fit; prove that order alone changed the bin count.

---
[← P-Median Facility Location](p_median.md) · [Back to Optimization library](README.md) · [Bin Packing: Best Fit →](bin_packing_best_fit.md)
