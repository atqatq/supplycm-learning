---
title: "Partial Autocorrelation (PACF) | supplycm Algorithm Library"
description: "Plain-English explanation of partial_autocorrelation from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, partial_autocorrelation, supply chain, plain english, forecasting"
---

# Partial Autocorrelation (PACF)

> **Call it:** `from supplycm.forecasting import partial_autocorrelation` · **Level:** Advanced · **You need:** basic arithmetic only

PACF asks the sharper question: after accounting for shorter lags, does THIS lag still add explanatory power? Lag-3 correlation might just be lag-1 echoing; PACF strips the echoes and shows the true direct connections - the blueprint for choosing model order.

**Think of it like this:** Family resemblance: kids resemble grandparents, but is that DIRECT or just via the parents? PACF controls for the parents and checks.

## When to reach for it

- Choosing the order (p) of AR models
- Separating direct effects from echoed correlations

## Try it with supplycm

```python
from supplycm.forecasting import partial_autocorrelation

result = partial_autocorrelation([10, 20, 15, 40, 12, 21, 16, 41, 11, 20, 15, 39], max_lag=5)
print(result)
```

You should see something like:

```text
[1.0, -0.4465, -0.0704, -0.758, 0.4859, -0.0311]
```

PACF values per lag - lags that stay large after others are controlled are the ones a model genuinely needs.

## Check yourself

1. PACF vs ACF - what does 'partial' remove?
2. A lag-4 ACF spike but no lag-4 PACF - interpretation?
3. How does PACF guide AR model building?

<details>
<summary>Show answers</summary>

1. The influence of intermediate lags - it isolates each lag's DIRECT contribution.

2. The seasonal echo travels through nearer lags - the direct connection is weaker than ACF suggests.

3. Significant PACF lags are candidate orders - when PACF cuts off after lag 2, try AR(2) first.

</details>

## Try this now

Compute both ACF and PACF on the same seasonal series; explain in two sentences what each caught that the other didn't.

---
[← Autocorrelation (ACF)](autocorrelation.md) · [Back to Forecasting library](README.md) · [Ljung-Box Test Statistic →](ljung_box_test.md)
