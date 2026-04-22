---
title: "P-Median Facility Location | supplycm Algorithm Library"
description: "Plain-English explanation of p_median from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, p_median, supply chain, plain english, optimization"
---

# P-Median Facility Location

> **Call it:** `from supplycm.optimization import p_median` · **Level:** Advanced · **You need:** basic arithmetic only

Choose exactly p facility locations among candidates to minimize total weighted DISTANCE to demand. Every customer rides to their nearest open facility. The classic 'where do the p warehouses go?' model - exact, interpretable, and quietly demanding computationally.

**Think of it like this:** Placing two clinics in a county: patients walk to the nearest, and the county minimizes total walking - the math decides siting without politics.

## When to reach for it

- Siting warehouses, clinics, or service points from candidates
- Median-style location questions where total access effort rules

## Try it with supplycm

```python
from supplycm.optimization import p_median

result = p_median(distances=[[0, 4, 6], [4, 0, 3], [6, 3, 0]], demand=[10, 20, 30], p=1)
print(result)
```

You should see something like:

```text
[[2], 120]
```

The chosen site and total weighted distance - open a second facility and watch the total collapse; that's the p-decision priced.

## Check yourself

1. What does the 'p' fix?
2. Why minimize weighted distance rather than the maximum?
3. How do you choose p wisely?

<details>
<summary>Show answers</summary>

1. The facility COUNT - the model optimizes WHERE given you've decided HOW MANY; p itself is a business decision.

2. P-median serves the AVERAGE customer well; covering the worst case is the p-CENTER's different philosophy.

3. Solve for p and p+1 and price the improvement - the curve of 'total distance vs facilities' makes the budget conversation honest.

</details>

## Try this now

Solve p=1 and p=2 on the example; compute each added facility's distance saving and pick your p with reasons.

---
[← Simplex Method (Linear Programming)](simplex_method.md) · [Back to Optimization library](README.md) · [Bin Packing: First Fit →](bin_packing_first_fit.md)
