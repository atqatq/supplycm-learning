---
title: "Gompertz Curve | supplycm Algorithm Library"
description: "Plain-English explanation of gompertz_trend from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, gompertz_trend, supply chain, plain english, forecasting"
---

# Gompertz Curve

> **Call it:** `from supplycm.forecasting import gompertz_trend` · **Level:** Advanced · **You need:** basic arithmetic only

The S-curve of adoption: slow start, rapid middle growth, then flattening at a ceiling. Gompertz fits all three phases from history and forecasts the rest of the journey - including the plateau management never wants to hear about.

**Think of it like this:** A video going viral and then fading: slow start, explosive middle, then everyone who cares has seen it.

## When to reach for it

- New products mid-adoption (who's left to convert?)
- Market sizing with a known saturation ceiling

## Try it with supplycm

```python
from supplycm.forecasting import gompertz_trend

result = gompertz_trend([5, 8, 14, 22, 30, 36, 40, 43], horizon=2)
print(result)
```

You should see something like:

```text
[18.9507, 0.4867, 0.2434, [17.679, 17.9463]]
```

Curve parameters plus forecasts near the plateau - the model is telling you growth is flattening toward a ceiling of roughly 45.

## Check yourself

1. What are the three phases of a Gompertz curve?
2. Why does the ceiling matter to planners?
3. When does fitting fail?

<details>
<summary>Show answers</summary>

1. Slow early adoption, rapid growth, saturation near the ceiling - the full life story of many products.

2. Capacity, inventory, and growth budgets must stop assuming the middle phase lasts forever.

3. If history only covers ONE phase - the model guesses the rest; early-stage fits are acts of faith.

</details>

## Try this now

Fit to a series clearly in the fast-growth phase only; observe the ceiling estimate - would you bet inventory on it?

---
[← Exponential Trend Forecast](exponential_trend_forecast.md) · [Back to Forecasting library](README.md) · [Logistic Curve →](logistic_trend.md)
