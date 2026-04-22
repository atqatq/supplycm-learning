---
title: "Set Cover (Greedy) | supplycm Algorithm Library"
description: "Plain-English explanation of set_cover_greedy from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, set_cover_greedy, supply chain, plain english, optimization"
---

# Set Cover (Greedy)

> **Call it:** `from supplycm.optimization import set_cover_greedy` · **Level:** Intermediate · **You need:** basic arithmetic only

Cover every requirement with the fewest facilities/warehouses/skills: repeatedly pick the option covering the most UNCOVERED requirements so far. Simple, fast, and provably within a logarithmic factor of optimal - the workhorse of 'minimum resources for full coverage'.

**Think of it like this:** Hiring a small team with all needed skills: each hire, choose the candidate covering the most missing skills - you staff the roster in a handful of picks.

## When to reach for it

- Minimum facilities/branches/DCs covering all demand zones
- Skill and coverage staffing decisions

## Try it with supplycm

```python
from supplycm.optimization import set_cover_greedy

result = set_cover_greedy(universe={1, 2, 3}, subsets={'A': {1, 2}, 'B': {2, 3}, 'C': {1}})
print(result)
```

You should see something like:

```text
['A', 'B']
```

The chosen sets ['A', 'B'] - two options cover everything; picking 'C' anywhere would have been waste.

## Check yourself

1. What does the greedy rule weigh at each step?
2. How far from optimal can greedy be?
3. Where does set cover hide in supply chains?

<details>
<summary>Show answers</summary>

1. New coverage per pick - the option disclosing the most unseen elements wins, regardless of its total size.

2. Within a log factor - theoretically loose, empirically close; the worst cases are constructed, not typical.

3. DC placement covering all regions, spare-part kits covering failure modes - every 'fewest resources, full coverage' question.

</details>

## Try this now

Build a 5-requirement instance with 4 candidate sets; run greedy, then try to beat it by hand - usually you can't.

---
[← Bin Packing: First Fit Decreasing (FFD)](bin_packing_first_fit_decreasing.md) · [Back to Optimization library](README.md)
