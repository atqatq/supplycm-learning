---
title: "Vogel's Approximation Method (VAM) | supplycm Algorithm Library"
description: "Plain-English explanation of vogels_approximation from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, vogels_approximation, supply chain, plain english, routing & transportation"
---

# Vogel's Approximation Method (VAM)

> **Call it:** `from supplycm.routing import vogels_approximation` · **Level:** Intermediate · **You need:** basic arithmetic only

The cleverest starting rule: for each row and column, compute the PENALTY of not using its cheapest lane (second-cheapest minus cheapest), then allocate wherever the penalty is highest. It anticipates regret - usually the best initial plan of the three classics.

**Think of it like this:** Choosing university offers by the cost of REJECTION: where falling to your second choice hurts most, decide there first.

## When to reach for it

- High-quality initial transportation plans
- Instances where starting quality saves real solver time

## Try it with supplycm

```python
from supplycm.routing import vogels_approximation

result = vogels_approximation(supply=[30, 50], demand=[20, 30, 30], costs=[[8, 6, 10], [9, 12, 13]])
print(result)
```

You should see something like:

```text
[[0.0, 30, 0.0], [20, 0.0, 30]]
```

An allocation built on regret-avoidance - compare its starting cost with least-cost's; VAM often opens ahead.

## Check yourself

1. What does the penalty (opportunity cost) capture?
2. Why is VAM often the best start?
3. Do better starts matter if MODI optimizes anyway?

<details>
<summary>Show answers</summary>

1. How much you lose by missing a lane's cheap rate - high-penalty rows get served first to avoid that regret.

2. It looks one decision ahead - greed on penalties beats plain greed on costs in most instances.

3. Fewer iterations to optimality - and in big or degenerate problems, that difference is very real.

</details>

## Try this now

Run all three methods on the same 3x4 problem; rank starting costs and count how far each sits from optimal.

---
[← Least Cost Method](least_cost_method.md) · [Back to Routing & Transportation library](README.md) · [MODI / Transportation Simplex →](transportation_simplex_modi.md)
