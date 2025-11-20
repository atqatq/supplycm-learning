---
title: "Linear Regression Forecast | supplycm Algorithm Library"
description: "Plain-English explanation of linear_regression_forecast from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, linear_regression_forecast, supply chain, plain english, forecasting"
---

# Linear Regression Forecast

> **Call it:** `from supplycm.forecasting import linear_regression_forecast` · **Level:** Intermediate · **You need:** basic arithmetic only

Fits the best straight line through your history and extends it: one slope, one intercept, honest and explainable. 'Sales grow about 12 units per month' is a sentence everyone can argue with productively. The backbone of business forecasting.

**Think of it like this:** Drawing the straightest line through scattered darts - then extending the line to predict where the next dart lands.

## When to reach for it

- Steady trending demand you can explain to anyone
- Quick trend sizing in S&OP reviews

## Try it with supplycm

```python
from supplycm.forecasting import linear_regression_forecast

result = linear_regression_forecast([100, 112, 121, 134, 145], horizon=3)
print(result)
```

You should see something like:

```text
[100.0, 11.2, [156.0, 167.2, 178.4]]
```

Slope, intercept, and the forecasts return - the line continues the +11-ish per-period climb into the next three periods.

## Check yourself

1. What do slope and intercept mean in business words?
2. When does a straight line lie?
3. How far would you trust a linear extrapolation?

<details>
<summary>Show answers</summary>

1. Slope: change per period; intercept: the line's starting point - together they say 'from here, growing this fast'.

2. When growth curves, saturates, or seasons - the line happily extrapolates nonsense beyond its evidence.

3. A few periods - and never past a known ceiling or turning point you can name.

</details>

## Try this now

Fit the line to 6 quarters of invented data, state the slope in one sentence, then forecast 2 quarters and sanity-check.

---
[← Pegels Classification](pegels_classification.md) · [Back to Forecasting library](README.md) · [Polynomial Regression Forecast →](polynomial_regression_forecast.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
