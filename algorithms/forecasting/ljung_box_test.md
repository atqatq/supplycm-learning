---
title: "Ljung-Box Test Statistic | supplycm Algorithm Library"
description: "Plain-English explanation of ljung_box_test from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, ljung_box_test, supply chain, plain english, forecasting"
---

# Ljung-Box Test Statistic

> **Call it:** `from supplycm.forecasting import ljung_box_test` · **Level:** Advanced · **You need:** basic arithmetic only

After fitting a model, the LEFTOVERS (residuals) should be boring - no pattern left. The Ljung-Box statistic tests exactly that: big values mean your residuals still carry autocorrelation, i.e. your model missed structure. A small statistic is the quiet applause of a good fit.

**Think of it like this:** Cleaning a room and checking for dust: Ljung-Box is the white-glove test - if the glove comes back dirty, clean again.

## When to reach for it

- Validating that a fitted model captured all structure
- Comparing two models' leftover cleanliness

## Try it with supplycm

```python
from supplycm.forecasting import ljung_box_test

result = ljung_box_test([0.5, -0.4, 0.6, -0.5, 0.4, -0.6, 0.5, -0.4, 0.6, -0.5, 0.4, -0.6], max_lag=4)
print(result)
```

You should see something like:

```text
41.2983
```

A statistic to compare against chi-square critical values at the chosen lag - here a large value says structure survives in the residuals.

## Check yourself

1. What do 'clean' residuals look like statistically?
2. Ljung-Box flags my model. First response?
3. Can a model pass Ljung-Box and still forecast badly?

<details>
<summary>Show answers</summary>

1. No autocorrelation at any lag - pure noise; all signal extracted.

2. Look at WHICH lags correlate - missing season or insufficient lag order usually reveals itself there.

3. Yes - it certifies pattern capture, not accuracy; keep checking error metrics too.

</details>

## Try this now

Fit a naive model to trending data, run Ljung-Box on residuals, and watch it catch the leftover trend.

---
[← Partial Autocorrelation (PACF)](partial_autocorrelation.md) · [Back to Forecasting library](README.md) · [ADF Test Statistic (Stationarity) →](adf_test.md)
