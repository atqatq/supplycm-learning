---
title: "MODI / Transportation Simplex | supplycm Algorithm Library"
description: "Plain-English explanation of transportation_simplex_modi from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, transportation_simplex_modi, supply chain, plain english, routing & transportation"
---

# MODI / Transportation Simplex

> **Call it:** `from supplycm.routing import transportation_simplex_modi` · **Level:** Advanced · **You need:** basic arithmetic only

The optimizer for shipping tables: from any feasible plan, compute hidden prices (MODI values) for each used lane, find a cell where shipping would SAVE money, shuffle quantities around a loop, and repeat until no cell offers savings. Guaranteed optimal endpoint.

**Think of it like this:** Renegotiating a shipping table lane by lane: every pass asks 'would rerouting via this empty lane save money?' - shuffling flows around loops until the answer is no.

## When to reach for it

- Optimizing multi-warehouse to multi-customer shipping plans
- The classical exact method behind transportation planning

## Try it with supplycm

```python
from supplycm.routing import transportation_simplex_modi

result = transportation_simplex_modi(supply=[30, 50], demand=[20, 30, 30], costs=[[8, 6, 10], [9, 12, 13]])
print(result)
```

You should see something like:

```text
[[[20, 10, 0.2], [0.2, 20, 30]], 853.8]
```

The optimized allocation and its total cost - the final table where no empty cell offers a cheaper reroute.

## Check yourself

1. What do MODI values (u, v) actually measure?
2. What is a 'loop' in the improvement step?
3. When does the algorithm stop?

<details>
<summary>Show answers</summary>

1. Implicit prices per origin and destination - their difference reveals each lane's true economic attractiveness.

2. The closed rectangle path that shifts quantities: add here, subtract there, keeping every row and column balanced.

3. When no empty cell has a negative improvement index - provably no cheaper allocation exists.

</details>

## Try this now

Start from the least-cost plan, run MODI, and identify which single cell swap delivered the saving.

---
[← Vogel's Approximation Method (VAM)](vogels_approximation.md) · [Back to Routing & Transportation library](README.md) · [Transshipment Problem →](transshipment_problem.md)
