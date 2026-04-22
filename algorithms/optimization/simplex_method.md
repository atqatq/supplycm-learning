---
title: "Simplex Method (Linear Programming) | supplycm Algorithm Library"
description: "Plain-English explanation of simplex_method from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, simplex_method, supply chain, plain english, optimization"
---

# Simplex Method (Linear Programming)

> **Call it:** `from supplycm.optimization import simplex_method` · **Level:** Advanced · **You need:** basic arithmetic only

The grandfather of optimization: maximize a linear objective under linear constraints by walking along the feasible region's CORNERS, each step improving, until no corner is better. Industrial planning ran on this for decades - and its shadow prices still run allocation meetings.

**Think of it like this:** Hunting the best corner of a fenced field: walk along the fence, always taking the segment that improves, until every direction left is worse - the best corner is provably where you stop.

## When to reach for it

- Product mix, blending, and allocation with linear costs
- Any planning model where constraints and goal are straight lines

## Try it with supplycm

```python
from supplycm.optimization import simplex_method

result = simplex_method(c=[3, 5], A=[[1, 0], [0, 2], [3, 2]], b=[4, 12, 18], maximize=True)
print(result)
```

You should see something like:

```text
[[2.0, 6.0], 36.0]
```

The optimal mix (2, 6) with objective 36 - plus the basis telling you which constraints bind; the shadow prices hide in the duals.

## Check yourself

1. Why walk only the CORNERS?
2. What are 'shadow prices' in the solution?
3. What CAN'T linear programming express?

<details>
<summary>Show answers</summary>

1. Linear objectives peak at vertices - checking every corner in an improving order guarantees the global optimum without interior wandering.

2. The worth of one extra unit of each constraint's resource - the dual values that convert a plan into an investment argument.

3. Fixed costs, minimums, and all-or-nothing logic - those bend lines into curves and require integer or nonlinear extensions.

</details>

## Try this now

Interpret which constraint binds at the optimum; loosen it slightly and verify the objective gain equals the shadow price.

---
[← Lagrange Multiplier](lagrange_multiplier.md) · [Back to Optimization library](README.md) · [P-Median Facility Location →](p_median.md)
