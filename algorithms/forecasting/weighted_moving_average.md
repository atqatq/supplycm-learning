---
title: "Weighted Moving Average | supplycm Algorithm Library"
description: "Plain-English explanation of weighted_moving_average from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, weighted_moving_average, supply chain, plain english, forecasting"
---

# Weighted Moving Average

> **Call it:** `from supplycm.forecasting import weighted_moving_average` · **Level:** Intermediate · **You need:** basic arithmetic only

A moving average with opinions: give recent periods bigger weights (0.5, 0.3, 0.2) so yesterday matters more than last week. You control the memory profile directly instead of letting a flat average treat all days equally.

**Think of it like this:** Asking three friends for advice but trusting the one who watched the market this week twice as much as the others.

## When to reach for it

- When recency clearly matters but you want explicit control
- Smoothing where a one-size weight profile fits your lead time

## Try it with supplycm

```python
from supplycm.forecasting import weighted_moving_average

result = weighted_moving_average([40, 45, 50], weights=[0.2, 0.3, 0.5])
print(result)
```

You should see something like:

```text
[None, None, 46.5]
```

The forecast leans toward the 50 - the 0.5 weight says recent evidence dominates; swap the weights and the answer flips.

## Check yourself

1. What must the weights sum to?
2. Weighted vs simple MA - when bother?
3. How is this related to exponential smoothing?

<details>
<summary>Show answers</summary>

1. 1.0 - so the forecast stays on the data's scale instead of inflating or shrinking.

2. When recent periods genuinely carry more information - the weights encode that belief explicitly.

3. Exponential smoothing is the infinite version: weights that decay forever by a constant factor.

</details>

## Try this now

Forecast with weights [0.6, 0.3, 0.1] vs [0.1, 0.3, 0.6] and explain the flip in one sentence.

---
[← Simple Moving Average (SMA)](simple_moving_average.md) · [Back to Forecasting library](README.md) · [Rolling Mean Forecast →](rolling_mean_forecast.md)
