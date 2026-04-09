---
title: "N-Queens Backtracking | supplycm Algorithm Library"
description: "Plain-English explanation of n_queens_backtracking from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, n_queens_backtracking, supply chain, plain english, optimization"
---

# N-Queens Backtracking

> **Call it:** `from supplycm.optimization import n_queens_backtracking` · **Level:** Advanced · **You need:** basic arithmetic only

Place N chess queens where none attacks another. Backtracking tries a placement, dives deeper, and undoes any choice that leads to conflict - the cleanest demonstration of 'try, verify, retreat, retry'. The pattern powers every constraint solver you'll ever meet.

**Think of it like this:** Filling a seating chart one guest at a time: place, check feuds, and when stuck, politely re-seat the LAST guest before scrapping everything.

## When to reach for it

- Learning systematic search with graceful undo
- The template for constraint problems: schedule, layout, assignment

## Try it with supplycm

```python
from supplycm.optimization import n_queens_backtracking

result = n_queens_backtracking(n=4)
print(result)
```

You should see something like:

```text
[1, 3, 0, 2]
```

A valid queen-per-row placement - no two share a column or diagonal; backtracking silently retreated from every dead end to find it.

## Check yourself

1. What is 'backtracking' in one sentence?
2. Why is undoing better than restarting?
3. Where does this pattern appear in real tools?

<details>
<summary>Show answers</summary>

1. Depth-first search with undo: commit to a choice, explore, and if the branch fails, revert cleanly and try the next.

2. All earlier good choices are preserved - you only unwind the failed decision, not the whole plan.

3. CP solvers, timetabling engines, robot path planners - anywhere 'constraints plus try-and-retreat' describes reality.

</details>

## Try this now

Solve 4-queens on paper with explicit backtracking; mark the two placements you had to undo and why.

---
[← Graph Coloring (Greedy)](graph_coloring_greedy.md) · [Back to Optimization library](README.md) · [Ant Colony Optimization (ACO) →](ant_colony_optimization.md)
