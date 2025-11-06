---
title: "Single Exponential Smoothing (SES) | supplycm Algorithm Library"
description: "Plain-English explanation of single_exponential_smoothing from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, single_exponential_smoothing, supply chain, plain english, forecasting"
---

# Single Exponential Smoothing (SES)

> **Call it:** `from supplycm.forecasting import single_exponential_smoothing` · **Level:** Beginner · **You need:** basic arithmetic only

The workhorse level forecaster: each new estimate blends the latest actual with the previous estimate - alpha says how much each gets. High alpha chases the present; low alpha trusts the accumulated past. No trend, no season - just a smart, adaptive level.

**Think of it like this:** Your opinion of a friend's mood: today's behavior (alpha) blended with everything you knew before (1 minus alpha).

## When to reach for it

- Stable demand without trend or seasonality
- The level engine inside Holt, Holt-Winters, and modern planners

## Try it with supplycm

```python
from supplycm.forecasting import single_exponential_smoothing

result = single_exponential_smoothing([40, 45, 42, 50, 48], alpha=0.3)
print(result)
```

You should see something like:

```text
[40.0, 41.5, 41.65, 44.155, 45.3085]
```

The smoothed series settles near the recent level - each step moves alpha of the gap, so jumps land gently.

## Check yourself

1. Alpha 0.2 vs 0.8 - personalities?
2. Why 'exponential'?
3. When is SES the WRONG tool?

<details>
<summary>Show answers</summary>

1. 0.2 is calm and laggy; 0.8 is nervous and reactive - choose by how fast the world actually changes.

2. Weights on older data shrink by a constant factor each step - an exponential decay of memory.

3. Clear trends (it lags) or seasons (it ignores) - upgrade to Holt or Holt-Winters then.

</details>

## Try this now

Run alpha 0.1 and 0.9 on data with a level shift; identify which one 'notices' first and at what cost.

---
[← Drift Method](drift_method.md) · [Back to Forecasting library](README.md) · [SES with Drift →](ses_with_drift.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
