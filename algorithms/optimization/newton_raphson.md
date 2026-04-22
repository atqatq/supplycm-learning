---
title: "Newton-Raphson | supplycm Algorithm Library"
description: "Plain-English explanation of newton_raphson from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, newton_raphson, supply chain, plain english, optimization"
---

# Newton-Raphson

> **Call it:** `from supplycm.optimization import newton_raphson` · **Level:** Advanced · **You need:** basic arithmetic only

Finding where a function crosses zero, using curvature: jump to where the tangent line hits zero, repeat. Convergence is spectacularly fast near the answer - quadratic, in fact - provided the derivative behaves. The oldest numerical workhorse still earning its keep.

**Think of it like this:** Zooming to a zero with a map AND a slope: instead of blind steps, you aim where the local straight-line says the zero must be - each jump is informed.

## When to reach for it

- Solving equations precisely (break-even roots, pricing equilibria)
- Any root-finding where derivatives are available and tame

## Try it with supplycm

```python
from supplycm.optimization import newton_raphson

result = newton_raphson(f=lambda x: x ** 2 - 4, df=lambda x: 2 * x, x0=1.0)
print(result)
```

You should see something like:

```text
2.0
```

The root near 2.0 - watch the speed: errors don't just shrink, they square, so digits of accuracy double per step.

## Check yourself

1. Why is Newton's convergence called 'quadratic'?
2. What's Newton's failure mode?
3. Root-finding vs minimizing - the connection?

<details>
<summary>Show answers</summary>

1. Roughly, the error squares each step - 0.1 becomes 0.01 becomes 0.0001; accuracy explodes near the root.

2. Bad derivatives or terrible starting points can cycle or diverge - the tangent can point somewhere absurd.

3. Minimizing f means finding where its DERIVATIVE is zero - apply Newton to the derivative and you get optimization (Newton's method in optimization).

</details>

## Try this now

Solve x^3 - 8 = 0 from x0 = 1 and x0 = 10; count steps each took and see how starting points matter.

---
[← Gradient Descent](gradient_descent.md) · [Back to Optimization library](README.md) · [Lagrange Multiplier →](lagrange_multiplier.md)
