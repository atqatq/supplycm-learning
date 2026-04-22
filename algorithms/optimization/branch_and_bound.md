---
title: "Branch and Bound | supplycm Algorithm Library"
description: "Plain-English explanation of branch_and_bound from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, branch_and_bound, supply chain, plain english, optimization"
---

# Branch and Bound

> **Call it:** `from supplycm.optimization import branch_and_bound` · **Level:** Advanced · **You need:** basic arithmetic only

Exact optimization with pruning: split the problem into branches, and whenever a branch's best HOPED-FOR value can't beat what you've already found, abandon it without exploring. Enumerates far less than brute force, yet still guarantees the true optimum when it finishes.

**Think of it like this:** Treasure hunting with a promise map: if a region's best possible loot is worse than what's already in your bag, skip the region entirely - no digging, no regret.

## When to reach for it

- Exact answers where brute force would take forever
- The engine inside MILP solvers (with linear programming relaxations)

## Try it with supplycm

```python
from supplycm.optimization import branch_and_bound

result = branch_and_bound(objective=lambda x: x[0] * x[1], lower_bound=[0, 0], upper_bound=[5, 5])
print(result)
```

You should see something like:

```text
[[5, 5], 25]
```

The optimal solution (5, 5) with value 25 - branches whose bounds couldn't beat it were pruned sight-unseen, and correctly.

## Check yourself

1. What makes a bound 'good enough to prune'?
2. Why is this better than brute enumeration?
3. What does the 'relaxation' contribute?

<details>
<summary>Show answers</summary>

1. If the branch's best CASE can't beat the incumbent solution, its actual case can't either - skip it with mathematical peace of mind.

2. Pruned branches cost nothing - the proof of optimality survives while most of the work vanishes.

3. It computes the branch's optimistic ceiling quickly (e.g., allowing fractional decisions) - tight ceilings prune hard; loose ones prune slowly.

</details>

## Try this now

Prune by hand on a 3-variable integer problem: compute each branch's optimistic bound and decide which branch you'd explore first.

---
[← Tabu Search](tabu_search.md) · [Back to Optimization library](README.md) · [Golden Section Search →](golden_section_search.md)
