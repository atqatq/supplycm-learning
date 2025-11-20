---
title: "VAR Model (Vector Autoregression) | supplycm Algorithm Library"
description: "Plain-English explanation of var_model from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, var_model, supply chain, plain english, forecasting"
---

# VAR Model (Vector Autoregression)

> **Call it:** `from supplycm.forecasting import var_model` · **Level:** Advanced · **You need:** basic arithmetic only

Two (or more) series that move each OTHER - like price and volume, or two linked products - deserve a model that captures the feedback. VAR regresses each series on BOTH series' history, returning coefficient matrices and intercepts. It is AR, thinking in duets.

**Think of it like this:** Two dance partners: each one's next step depends on their own momentum AND where the other just moved - VAR models the partnership.

## When to reach for it

- Linked SKUs (substitutes, complements) with shared history
- Price-volume or cross-market feedback effects

## Try it with supplycm

```python
from supplycm.forecasting import var_model

result = var_model(series=[[100, 104, 103, 108, 112], [50, 48, 52, 49, 47]])
print(result)
```

You should see something like:

```text
[[[1.2071, 1.4051], [-0.2424, -0.6303]], [-88.3848, 105.5091]]
```

Coefficient matrix and intercepts return - entries crossing between the two series reveal who influences whom, and how strongly.

## Check yourself

1. When does VAR beat two separate AR models?
2. What does a near-zero cross coefficient mean?
3. What's the data appetite for VAR?

<details>
<summary>Show answers</summary>

1. When the series influence each other - ignoring the feedback loses real predictive signal.

2. No influence in that direction - the 'partnership' is really a solo act.

3. Hungry - two series means two coefficient sets per lag; short histories make noisy estimates.

</details>

## Try this now

Model a substitute pair (price of tea vs coffee demand) with invented data; interpret the cross-coefficients aloud.

---
[← MA Model (Moving Average Process)](ma_model.md) · [Back to Forecasting library](README.md) · [Autocorrelation (ACF) →](autocorrelation.md)
