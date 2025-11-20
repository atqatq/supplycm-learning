---
title: "AR Model (Autoregressive) | supplycm Algorithm Library"
description: "Plain-English explanation of ar_model from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, ar_model, supply chain, plain english, forecasting"
---

# AR Model (Autoregressive)

> **Call it:** `from supplycm.forecasting import ar_model` · **Level:** Advanced · **You need:** basic arithmetic only

An AR model forecasts tomorrow as a weighted recipe of recent history: 'tomorrow = 0.5 x today + 0.3 x yesterday + base'. The function returns those coefficients. It captures momentum and mean-reversion patterns that smoothing methods blur over.

**Think of it like this:** Predicting your running pace from your last few splits: yesterday's pace matters most, the day before less, with an eye on your usual average.

## When to reach for it

- Series where recent values genuinely predict the next
- Understanding momentum effects before choosing smoother methods

## Try it with supplycm

```python
from supplycm.forecasting import ar_model

result = ar_model([100, 104, 103, 108, 112, 111, 116], order=1)
print(result)
```

You should see something like:

```text
[[0.4516], 107.7143]
```

A coefficient near 0.5 with an intercept near the mean - each forecast leans halfway back to the average, a mean-reverting signature.

## Check yourself

1. What does an AR coefficient of 1 vs 0 imply?
2. Why fit AR when SES exists?
3. What breaks AR models?

<details>
<summary>Show answers</summary>

1. Near 1: momentum - yesterday persists (random-walk-like). Near 0: mean reversion - today's spike is noise, the average beckons.

2. AR tells you HOW the past propagates (coefficients you can inspect); SES just smooths without explaining.

3. Structural breaks - coefficients learned on the old regime misfire after the world changes.

</details>

## Try this now

Fit AR(1) to a strongly trending series and observe how it under-predicts; explain why momentum-free reversion lags trends.

---
[← Theta Method](theta_method.md) · [Back to Forecasting library](README.md) · [MA Model (Moving Average Process) →](ma_model.md)
