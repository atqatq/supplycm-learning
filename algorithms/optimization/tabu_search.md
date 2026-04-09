---
title: "Tabu Search | supplycm Algorithm Library"
description: "Plain-English explanation of tabu_search from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, tabu_search, supply chain, plain english, optimization"
---

# Tabu Search

> **Call it:** `from supplycm.optimization import tabu_search` · **Level:** Advanced · **You need:** basic arithmetic only

Local search with a memory: keep a short 'tabu list' of recent moves and FORBID reversing them, forcing the search out of loops and through worse terrain to reach new regions. Sometimes you must walk backward to go forward - tabu makes that legal and temporary.

**Think of it like this:** A hiker who marks the trails they just tried: never immediately backtracking forces exploration of new ridgelines instead of pacing the same ledge.

## When to reach for it

- Sequencing problems where local optima cluster tightly
- Any improvement search plagued by circular wandering

## Try it with supplycm

```python
from supplycm.optimization import tabu_search

result = tabu_search(objective=lambda x: -sum(x), initial=[0, 0], neighbors=lambda x: [[x[0] + 1, x[1]], [x[0], x[1] + 1], [x[0] - 1, x[1]], [x[0], x[1] - 1]], tabu_size=3, max_iter=20)
print(result)
```

You should see something like:

```text
[[20, 0], -20]
```

The best solution found - the tabu list quietly vetoed backtracking moves, pushing the search outward consistently.

## Check yourself

1. What does the tabu list actually store?
2. How does the search escape local optima?
3. Why a SHORT memory?

<details>
<summary>Show answers</summary>

1. Recent moves (or attributes) - short-term memory forbidding their immediate reversal; the loop-breaker.

2. It accepts worsening moves when the improving ones are forbidden - wandering is the price of novelty.

3. Long tabus over-constrain; short ones may loop - the list length is the exploration-exploitation dial in disguise.

</details>

## Try this now

Set tabu_size to 1 and 10 on a small instance; observe looping versus over-constraint and pick your favorite.

---
[← Simulated Annealing (SA)](simulated_annealing.md) · [Back to Optimization library](README.md) · [Branch and Bound →](branch_and_bound.md)
