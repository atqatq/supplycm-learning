---
title: "Naive Forecast | supplycm Algorithm Library"
description: "Plain-English explanation of naive_forecast from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, naive_forecast, supply chain, plain english, forecasting"
---

# Naive Forecast

> **Call it:** `from supplycm.forecasting import naive_forecast` · **Level:** Beginner · **You need:** basic arithmetic only

Copy the last actual value and use it as the next forecast. That is the entire method - and that is its charm. It is free, instant, surprisingly hard to beat on stable data, and the benchmark every fancier method must justify itself against.

**Think of it like this:** Assuming tomorrow's weather equals today's: often right, sometimes spectacularly wrong, never expensive to compute.

## When to reach for it

- A baseline to compare all other forecasts against
- Very stable demand where fancy methods just add noise

## Try it with supplycm

```python
from supplycm.forecasting import naive_forecast

result = naive_forecast([40, 45, 42, 50, 48])
print(result)
```

You should see something like:

```text
[None, 40.0, 45.0, 42.0, 50.0]
```

Each forecast equals the previous actual; the first slot is empty because nothing precedes the first day.

## Check yourself

1. What is the naive forecast for tomorrow?
2. Why keep a method this simple around?
3. When does naive fail hardest?

<details>
<summary>Show answers</summary>

1. Today's actual value - copied forward unchanged.

2. It is the fairness benchmark: if your elaborate model can't beat it, the model isn't earning its complexity.

3. Trends and seasonality - it always lags one step behind any pattern.

</details>

## Try this now

Forecast 5 periods of invented data naively; then beat it with a moving average and prove the win with MAE.

---
[Back to Forecasting library](README.md) · [Seasonal Naive Forecast →](seasonal_naive_forecast.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
