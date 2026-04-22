---
title: "Lagrange Multiplier | supplycm Algorithm Library"
description: "Plain-English explanation of lagrange_multiplier from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, lagrange_multiplier, supply chain, plain english, optimization"
---

# Lagrange Multiplier

> **Call it:** `from supplycm.optimization import lagrange_multiplier` · **Level:** Advanced · **You need:** basic arithmetic only

Optimize a goal while respecting a constraint - by pricing the constraint. The multiplier lambda is the shadow price: how much the objective would improve per unit of relaxed constraint. The function searches for the point where goal and constraint balance perfectly.

**Think of it like this:** A chef maximizing deliciousness under a salt budget: lambda is the value of 'one more gram of salt' - when the marginal flavor per gram equals the constraint's price, the dish is optimal.

## When to reach for it

- Constrained optimization with a single binding constraint
- Understanding shadow prices - the economics inside every constrained optimum

## Try it with supplycm

```python
from supplycm.optimization import lagrange_multiplier

result = lagrange_multiplier(objective=lambda x: x[0] + x[1], constraint=lambda x: x[0] + x[1] - 10, initial=[5.0, 5.0])
print(result)
```

You should see something like:

```text
[[3.6318, 3.6318], 7.2635]
```

The balanced point and lambda - read lambda as the marginal value of loosening the constraint by one unit.

## Check yourself

1. What does the multiplier lambda MEAN economically?
2. Why do gradient-based solvers need this machinery?
3. Where do shadow prices show up in business?

<details>
<summary>Show answers</summary>

1. Shadow price: the objective's improvement per unit of extra constraint - capacity value, budget value, made numeric.

2. Constraints block naive downhill walking - the multiplier folds the fence into the landscape so gradients stay honest.

3. CPLEX-style reports: 'one more hour of machine time is worth X' - every planner should read lambda before buying capacity.

</details>

## Try this now

Tighten the constraint by 1 and re-solve; verify the objective change matches the lambda you were shown.

---
[← Newton-Raphson](newton_raphson.md) · [Back to Optimization library](README.md) · [Simplex Method (Linear Programming) →](simplex_method.md)
