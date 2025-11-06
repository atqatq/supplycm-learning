---
title: "Seasonal Naive Forecast | supplycm Algorithm Library"
description: "Plain-English explanation of seasonal_naive_forecast from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, seasonal_naive_forecast, supply chain, plain english, forecasting"
---

# Seasonal Naive Forecast

> **Call it:** `from supplycm.forecasting import seasonal_naive_forecast` · **Level:** Beginner · **You need:** basic arithmetic only

The naive method with a memory: forecast next period with the value from the SAME season last cycle. December comes from last December, Monday from last Monday. For strongly seasonal products it embarrasses fancier methods at zero effort.

**Think of it like this:** A calendar that repeats: whatever happened on this date last year, plan for again.

## When to reach for it

- Holiday-driven products (toys, decorations, sunscreen)
- Strong weekly patterns (weekend cafe peaks)

## Try it with supplycm

```python
from supplycm.forecasting import seasonal_naive_forecast

result = seasonal_naive_forecast([100, 105, 110, 300, 102, 106, 112, 310], season_length=4)
print(result)
```

You should see something like:

```text
[None, None, None, None, 100.0, 105.0, 110.0, 300.0]
```

Period 5 gets 100 (from period 1), period 6 gets 105 - the seasonal fingerprint of cycle 1 is projected onto cycle 2.

## Check yourself

1. How does it differ from plain naive?
2. What breaks it?
3. Why is it the right baseline for seasonal items?

<details>
<summary>Show answers</summary>

1. It copies from one season AGO, not one period ago - preserving the pattern naive destroys.

2. Trends (last year's level is stale) and shifting seasonality - the calendar repeats, the world doesn't always.

3. Because comparing a seasonal model against plain naive is a rigged game - the seasonal baseline is the honest opponent.

</details>

## Try this now

Forecast 4 periods of a weekly pattern (period 7) where Saturdays spike 3x; check the method's picks.

---
[← Naive Forecast](naive_forecast.md) · [Back to Forecasting library](README.md) · [Average Method →](average_method.md)
