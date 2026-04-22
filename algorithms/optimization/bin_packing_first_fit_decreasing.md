---
title: "Bin Packing: First Fit Decreasing (FFD) | supplycm Algorithm Library"
description: "Plain-English explanation of bin_packing_first_fit_decreasing from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, bin_packing_first_fit_decreasing, supply chain, plain english, optimization"
---

# Bin Packing: First Fit Decreasing (FFD)

> **Call it:** `from supplycm.optimization import bin_packing_first_fit_decreasing` · **Level:** Intermediate · **You need:** basic arithmetic only

The famously effective upgrade: SORT items biggest-first, then apply first fit. Big awkward items get placed while bins are empty, small items fill the seams. FFD's guarantee is startlingly good - within about 22% of optimal on any instance.

**Think of it like this:** Packing the car for a trip: suitcases in first while the trunk is empty, then bags and cables poured into every remaining crevice.

## When to reach for it

- The default packing heuristic when order is under your control
- Pallet building, container loading, job batching

## Try it with supplycm

```python
from supplycm.optimization import bin_packing_first_fit_decreasing

result = bin_packing_first_fit_decreasing(items=[4, 8, 1, 4, 2, 1], bin_capacity=10)
print(result)
```

You should see something like:

```text
[[8, 2], [4, 4, 1, 1]]
```

Bins with the 8 placed first - compare with plain first-fit on the same items; sorting usually pays for itself instantly.

## Check yourself

1. Why does sorting biggest-first help so much?
2. What's FFD's guarantee?
3. When is FFD still beaten?

<details>
<summary>Show answers</summary>

1. Reversibility: small items fit almost anywhere, big ones almost nowhere - place the inflexible first, improvise with the rest.

2. At most 11/9 of optimal bins (plus a little) - a heuristic with a proof, which is rare and lovely.

3. Awkward item mixes where optimal requires NOT placing greedily - exact methods win small instances; FFD wins everything else in practice.

</details>

## Try this now

Construct a 6-item instance where FFD uses one bin more than optimal; verify by trying the alternative packing by hand.

---
[← Bin Packing: Best Fit](bin_packing_best_fit.md) · [Back to Optimization library](README.md) · [Set Cover (Greedy) →](set_cover_greedy.md)
