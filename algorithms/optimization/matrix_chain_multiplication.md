---
title: "Matrix Chain Multiplication | supplycm Algorithm Library"
description: "Plain-English explanation of matrix_chain_multiplication from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, matrix_chain_multiplication, supply chain, plain english, optimization"
---

# Matrix Chain Multiplication

> **Call it:** `from supplycm.optimization import matrix_chain_multiplication` · **Level:** Advanced · **You need:** basic arithmetic only

Multiplying a chain of matrices, the GROUPING changes the cost wildly: (AB)C can be cheap where A(BC) is expensive. DP finds the cheapest parenthesization. In practice: the classic model for 'the ORDER of combining steps changes total work' - batching, joins, and consolidation.

**Think of it like this:** Planning a renovation: doing rooms in one grouping lets you reuse scaffolding; another grouping triples setup work - same tasks, wildly different totals.

## When to reach for it

- Understanding why operation ORDER changes total effort
- The canonical DP example for sequence decisions

## Try it with supplycm

```python
from supplycm.optimization import matrix_chain_multiplication

result = matrix_chain_multiplication(dims=[1, 2, 3, 4])
print(result)
```

You should see something like:

```text
18
```

The minimum cost 18 - the cheap grouping found by the table; try the alternative grouping by hand and feel the difference.

## Check yourself

1. Why does grouping matter at all?
2. How does DP structure the search?
3. What's the supply chain analogy?

<details>
<summary>Show answers</summary>

1. Intermediate result SIZES differ - multiplying by a huge intermediate repeatedly is expensive; good grouping keeps intermediates small.

2. Best cost for every (start, end) chain segment, built bottom-up - every split point gets its fair trial.

3. Consolidation order: which shipments merge first determines intermediate handling sizes - the same combinatorial spine.

</details>

## Try this now

Compute the cost of both groupings for dims [1, 2, 3, 4] by hand; confirm one beats the other and by how much.

---
[← Longest Common Subsequence](dynamic_programming_lcs.md) · [Back to Optimization library](README.md) · [Convex Hull →](convex_hull.md)
