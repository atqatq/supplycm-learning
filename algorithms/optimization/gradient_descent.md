---
title: "Gradient Descent | supplycm Algorithm Library"
description: "Plain-English explanation of gradient_descent from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, gradient_descent, supply chain, plain english, optimization"
---

# Gradient Descent

> **Call it:** `from supplycm.optimization import gradient_descent` · **Level:** Intermediate · **You need:** basic arithmetic only

Walk downhill: measure the slope (gradient) at your position, step the opposite way, repeat. Learning rate is the stride - too big and you leap over the valley, too small and you crawl. The engine under modern machine learning, and a fine optimizer for smooth business objectives.

**Think of it like this:** Descending a hill in fog: you can't see the summit, but you can feel the slope under your feet - take a step downhill, repeat, and the valley finds you.

## When to reach for it

- Smooth objectives with computable gradients
- The conceptual engine behind every fitted model you use

## Try it with supplycm

```python
from supplycm.optimization import gradient_descent

result = gradient_descent(objective=lambda x: (x[0] - 2) ** 2 + (x[1] + 1) ** 2, initial=[0.0, 0.0], learning_rate=0.1, max_iter=500)
print(result)
```

You should see something like:

```text
[[1.9969, -0.9985], 0.0]
```

The solution near (2, -1) with a tiny objective value - hundreds of honest downhill steps, each one simple.

## Check yourself

1. What does the learning rate actually control?
2. Where does gradient descent get stuck?
3. Why does it dominate machine learning?

<details>
<summary>Show answers</summary>

1. Step size - large strides overshoot and oscillate; small ones converge reliably but slowly; it's the patience dial.

2. Local minima and saddle points on non-convex landscapes - it is honest but nearsighted.

3. Objectives are smooth and gradients are computable - and the rule scales to billions of parameters without cleverness.

</details>

## Try this now

Run with learning_rate 0.01 vs 0.9 on the same problem; narrate the crawl and the oscillation you see.

---
[← Golden Section Search](golden_section_search.md) · [Back to Optimization library](README.md) · [Newton-Raphson →](newton_raphson.md)
