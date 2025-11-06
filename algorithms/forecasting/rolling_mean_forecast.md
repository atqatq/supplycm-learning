---
title: "Rolling Mean Forecast | supplycm Algorithm Library"
description: "Plain-English explanation of rolling_mean_forecast from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, rolling_mean_forecast, supply chain, plain english, forecasting"
---

# Rolling Mean Forecast

> **Call it:** `from supplycm.forecasting import rolling_mean_forecast` · **Level:** Beginner · **You need:** basic arithmetic only

Like the moving average, but built for rolling forward: it computes the mean of the last window and projects it across a forecast horizon. Same smoothing instinct, with multi-step output for planning several periods ahead.

**Think of it like this:** Averages your last three paychecks and budgets the next several months on that figure.

## When to reach for it

- Multi-period planning from a stable recent window
- Baseline projections in S&OP templates

## Try it with supplycm

```python
from supplycm.forecasting import rolling_mean_forecast

result = rolling_mean_forecast([40, 45, 42, 50, 48], window=3, horizon=3)
print(result)
```

You should see something like:

```text
[46.6667, 46.6667, 46.6667]
```

Three future periods all receive the same rolling average - a flat but honest projection of recent history.

## Check yourself

1. What happens to the forecast if one crazy value enters the window?
2. Why do all horizon periods get the same number?
3. When would you extend the window before forecasting?

<details>
<summary>Show answers</summary>

1. It contaminates all horizon periods until the window slides past - a known cost of simple averaging.

2. The method projects a LEVEL, not a trend - flat futures are its honest opinion.

3. When noise is high and you value stability over responsiveness.

</details>

## Try this now

Forecast horizon 4 with window 4 after a demand spike - watch the spike echo and explain how long it lingers.

---
[← Weighted Moving Average](weighted_moving_average.md) · [Back to Forecasting library](README.md) · [Moving Median Filter →](moving_median_filter.md)
