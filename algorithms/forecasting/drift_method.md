---
title: "Drift Method | supplycm Algorithm Library"
description: "Plain-English explanation of drift_method from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, drift_method, supply chain, plain english, forecasting"
---

# Drift Method

> **Call it:** `from supplycm.forecasting import drift_method` · **Level:** Intermediate · **You need:** basic arithmetic only

The naive forecast plus a trend: measure the average change per period over all history (the drift), then extend that slope into the future. First and last points set the slope - simple, surprisingly strong on trending data.

**Think of it like this:** Extrapolating your commute: it took 20 minutes and got 1 minute worse each month - plan for 25 next month.

## When to reach for it

- Steady trending demand without seasonality
- A strong trend-aware baseline that beats naive honestly

## Try it with supplycm

```python
from supplycm.forecasting import drift_method

result = drift_method([100, 110, 120, 130, 140], horizon=3)
print(result)
```

You should see something like:

```text
[150.0, 160.0, 170.0]
```

Forecasts extend the +10-per-period drift: 150, 160, 170 - first point to last point, averaged.

## Check yourself

1. How is drift computed?
2. What happens if the early history was atypical?
3. When does drift beat a fitted regression line?

<details>
<summary>Show answers</summary>

1. Total change (last minus first) divided by the number of steps - the average slope of the whole history.

2. The slope distorts - drift anchors on the endpoints, so outliers at either end steer everything.

3. Often never exactly - but with 2 data points of computation it gets remarkably close on clean trends.

</details>

## Try this now

Apply drift to [50, 55, 60, 200] and expose the endpoint-anchoring weakness; then fix the input and compare.

---
[← Moving Median Filter](moving_median_filter.md) · [Back to Forecasting library](README.md) · [Single Exponential Smoothing (SES) →](single_exponential_smoothing.md)
