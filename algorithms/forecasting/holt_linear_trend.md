---
title: "Holt's Linear Trend | supplycm Algorithm Library"
description: "Plain-English explanation of holt_linear_trend from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, holt_linear_trend, supply chain, plain english, forecasting"
---

# Holt's Linear Trend

> **Call it:** `from supplycm.forecasting import holt_linear_trend` · **Level:** Intermediate · **You need:** basic arithmetic only

Holt runs TWO smoothing engines at once: alpha tracks the level, beta tracks the trend. The forecast extends that live trend line forward. It is SES with a compass - the natural upgrade once demand clearly slopes.

**Think of it like this:** Tracking a hiker's position AND walking speed - extrapolate both, and you know where they'll be by dusk.

## When to reach for it

- Steady upward or downward demand trends
- Products in growth or decline phases

## Try it with supplycm

```python
from supplycm.forecasting import holt_linear_trend

result = holt_linear_trend([100, 110, 122, 131, 141], alpha=0.5, beta=0.1)
print(result)
```

You should see something like:

```text
[[100.0, 110.0, 121.0, 131.05, 141.0725], [10.0, 10.0, 10.1, 10.095, 10.0877]]
```

Two series come back - level and trend - and the trend estimate settles near +10 per period, matching the true slope.

## Check yourself

1. What do alpha and beta control separately?
2. Beta too high - symptom?
3. Why damp the trend for long horizons?

<details>
<summary>Show answers</summary>

1. Alpha: how fast the level adapts; beta: how fast the trend estimate adapts.

2. The trend estimate whipsaws with every noise blip, making forecasts seasick.

3. Real trends rarely run forever - undamped Holt shoots to absurd futures within a few periods.

</details>

## Try this now

Fit Holt to a series that grows then flattens; watch the trend engine overshoot and explain the fix.

---
[← SES with Drift](ses_with_drift.md) · [Back to Forecasting library](README.md) · [Dampened Trend Method →](dampened_trend.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
