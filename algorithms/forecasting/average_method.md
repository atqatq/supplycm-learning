---
title: "Average Method | supplycm Algorithm Library"
description: "Plain-English explanation of average_method from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, average_method, supply chain, plain english, forecasting"
---

# Average Method

> **Call it:** `from supplycm.forecasting import average_method` · **Level:** Beginner · **You need:** basic arithmetic only

Forecast every future period with the average of ALL history. One number, repeated forever. For stable products it is a rock; for trending or seasonal data it paints the future in one flat color - which is exactly its weakness.

**Think of it like this:** A thermostat stuck on the average temperature of the past year - fine in spring, absurd in January.

## When to reach for it

- Mature, stable products with no direction
- A baseline for judging whether trend methods add value

## Try it with supplycm

```python
from supplycm.forecasting import average_method

result = average_method([40, 45, 42, 50, 48], horizon=3)
print(result)
```

You should see something like:

```text
[45.0, 45.0, 45.0]
```

All three future periods get the same value - the historical mean; simple, transparent, immune to last-period noise.

## Check yourself

1. When does the average method beat naive?
2. Why does it fail on trends?
3. What does 'flat forever' imply about its assumptions?

<details>
<summary>Show answers</summary>

1. When data is noisy but stable - averaging damps the noise naive would copy.

2. It anchors on the historical middle while the world has moved - forecasts are systematically stale.

3. No trend, no seasonality, constant level - state those assumptions out loud before trusting it.

</details>

## Try this now

Apply it to trending data [10, 12, 14, 16, 18] and quantify how badly it under-forecasts period 5.

---
[← Seasonal Naive Forecast](seasonal_naive_forecast.md) · [Back to Forecasting library](README.md) · [Simple Moving Average (SMA) →](simple_moving_average.md)
