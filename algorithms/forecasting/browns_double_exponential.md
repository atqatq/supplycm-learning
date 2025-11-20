---
title: "Brown's Double Exponential Smoothing | supplycm Algorithm Library"
description: "Plain-English explanation of browns_double_exponential from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, browns_double_exponential, supply chain, plain english, forecasting"
---

# Brown's Double Exponential Smoothing

> **Call it:** `from supplycm.forecasting import browns_double_exponential` · **Level:** Intermediate · **You need:** basic arithmetic only

Holt's trend tracking with a clever trick: smooth the series TWICE, and estimate the trend from the GAP between the two smoothings. One parameter (alpha) drives everything - simpler to tune than Holt's two, at the cost of some flexibility.

**Think of it like this:** Watching a hiker through two binocular zoom levels: the difference between the sharp view and the blurred one reveals how fast they're moving.

## When to reach for it

- Trending data with no patience for tuning two parameters
- A one-knob trend-aware alternative to Holt

## Try it with supplycm

```python
from supplycm.forecasting import browns_double_exponential

result = browns_double_exponential([10, 12, 14, 15, 18], alpha=0.3, horizon=2)
print(result)
```

You should see something like:

```text
[17.269, 18.1766]
```

Forecasts above the last level - the double-smoothing gap exposed the trend and projected it forward.

## Check yourself

1. How does the trend hide in double smoothing?
2. One parameter vs Holt's two - trade-off?
3. When would you step up to Holt?

<details>
<summary>Show answers</summary>

1. The second smoothing lags the first on trending data - the gap grows with the slope, so the gap IS the trend estimate.

2. Simplicity and robustness vs flexibility - Brown's can't weight level and trend adaptation separately.

3. When trend changes abruptly and one knob can't track both level and slope quickly enough.

</details>

## Try this now

Compare Brown's double and Holt on the same trending series; check which tracks a mid-series trend change better.

---
[← Logistic Curve](logistic_trend.md) · [Back to Forecasting library](README.md) · [Brown's Triple Exponential Smoothing →](browns_triple_exponential.md)
