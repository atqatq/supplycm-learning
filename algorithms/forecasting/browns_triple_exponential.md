---
title: "Brown's Triple Exponential Smoothing | supplycm Algorithm Library"
description: "Plain-English explanation of browns_triple_exponential from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, browns_triple_exponential, supply chain, plain english, forecasting"
---

# Brown's Triple Exponential Smoothing

> **Call it:** `from supplycm.forecasting import browns_triple_exponential` · **Level:** Advanced · **You need:** basic arithmetic only

The same idea one level deeper: smooth THREE times, and the two gaps between the three smoothings jointly reveal both trend and curvature. One alpha still rules all - and the method can follow bending trends that double smoothing underestimates.

**Think of it like this:** Three camera zooms instead of two: the pattern of blur differences now reveals not just speed but ACCELERATION - the hiker is speeding up or slowing down.

## When to reach for it

- Data where the trend itself curves (accelerating growth/decline)
- Quadratic-style smoothing with a single tuning knob

## Try it with supplycm

```python
from supplycm.forecasting import browns_triple_exponential

result = browns_triple_exponential([10, 12, 14, 15, 18], alpha=0.2, horizon=2)
print(result)
```

You should see something like:

```text
[17.592, 18.8806]
```

Forecasts extending with slight curvature - the triple-smoothing gaps priced in the bend that double smoothing would have flattened.

## Check yourself

1. What does the third smoothing add?
2. Why keep alpha LOW here?
3. Relationship to Holt-Winters?

<details>
<summary>Show answers</summary>

1. Curvature awareness - two gaps instead of one, enough to estimate a bending (quadratic) trajectory.

2. Triple smoothing compounds reactivity - a high alpha triples down on noise; calm parameters keep the estimate stable.

3. Different lineage: Holt-Winters smooths components separately with three knobs; Brown's chains one knob through multiple passes - same goal, opposite philosophy.

</details>

## Try this now

Feed an accelerating series (differences that grow) to both Brown's variants; verify only the triple version bends with it.

---
[← Brown's Double Exponential Smoothing](browns_double_exponential.md) · [Back to Forecasting library](README.md) · [Theta Method →](theta_method.md)
