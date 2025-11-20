---
title: "Exponential Trend Forecast | supplycm Algorithm Library"
description: "Plain-English explanation of exponential_trend_forecast from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, exponential_trend_forecast, supply chain, plain english, forecasting"
---

# Exponential Trend Forecast

> **Call it:** `from supplycm.forecasting import exponential_trend_forecast` · **Level:** Intermediate · **You need:** basic arithmetic only

For growth that COMPOUNDS - each period grows by a percentage, not a fixed amount. The fit estimates the growth rate and projects it multiplicatively: 10%, then 11%, then 12.1... Matches businesses that scale, at least while they scale.

**Think of it like this:** Compound interest: money doesn't grow by 10 dollars forever - it grows by 10% of whatever it has.

## When to reach for it

- Products in percentage-growth phases
- Viral adoption, market expansion, inflation-indexed volumes

## Try it with supplycm

```python
from supplycm.forecasting import exponential_trend_forecast

result = exponential_trend_forecast([100, 110, 121, 133, 146], horizon=3)
print(result)
```

You should see something like:

```text
[100.0561, 1.0993, [160.6297, 176.5804, 194.1149]]
```

Growth rate near 10% per period with forecasts 160+, 176+, 194+ - compounding continues until you decide otherwise.

## Check yourself

1. Linear +10 vs exponential +10% - when do they diverge?
2. Why do exponential extrapolations embarrass forecasters?
3. What's the honest way to use it?

<details>
<summary>Show answers</summary>

1. Quickly! At level 500, linear adds 10 but exponential adds 50 - the curves split within a few periods.

2. Nothing compounds forever - markets saturate; the model doesn't know that unless you tell it.

3. Short horizons while growth is real, with a documented story for when the compounding stops.

</details>

## Try this now

Fit to [200, 220, 242, 266] and forecast 5 periods; then describe in words the assumption you just made.

---
[← Polynomial Regression Forecast](polynomial_regression_forecast.md) · [Back to Forecasting library](README.md) · [Gompertz Curve →](gompertz_trend.md)
