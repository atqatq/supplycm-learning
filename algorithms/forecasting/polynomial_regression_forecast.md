---
title: "Polynomial Regression Forecast | supplycm Algorithm Library"
description: "Plain-English explanation of polynomial_regression_forecast from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, polynomial_regression_forecast, supply chain, plain english, forecasting"
---

# Polynomial Regression Forecast

> **Call it:** `from supplycm.forecasting.polynomial_regression_forecast import polynomial_regression_forecast` · **Level:** Advanced · **You need:** basic arithmetic only

A flexible curve instead of a straight line - it can bend with accelerating or decelerating growth. Powerful, but dangerous: high-degree polynomials will wiggle wildly to touch every point, then explode outside the data. Use low degrees and squint suspiciously.

**Think of it like this:** A tailor who can take in ANY measurement - but ask for too many adjustments and the suit fits the past person, not the future one.

## When to reach for it

- Demand with visible curvature (S-curve starts, saturation)
- Interpolating within the range you have data for

## Try it with supplycm

```python
from supplycm.forecasting.polynomial_regression_forecast import polynomial_regression_forecast

result = polynomial_regression_forecast([5, 9, 16, 26, 39, 55], degree=2, horizon=3)
print(result)
```

You should see something like:

```text
[74.0, 96.0, 121.0]
```

The curve bends upward through the accelerating data - its forecasts continue the bend; watch what happens beyond the last point.

## Check yourself

1. Why do high-degree polynomials explode?
2. Degree 2 vs degree 5 - which would you defend?
3. How is this different from exponential trend fitting?

<details>
<summary>Show answers</summary>

1. They gain a wobble for every extra degree - outside the data range, those wobbles amplify into absurd values.

2. 2 - a gentle bend is usually real physics (growth, saturation); degree 5 is usually the data's biography, not its future.

3. Polynomial bends by arithmetic; exponential compounds by percentage - the mechanics of growth differ.

</details>

## Try this now

Fit degrees 1, 2, 3 to the same S-curve-ish data and compare 4-period-ahead forecasts - identify the overfitter.

---
[← Linear Regression Forecast](linear_regression_forecast.md) · [Back to Forecasting library](README.md) · [Exponential Trend Forecast →](exponential_trend_forecast.md)
