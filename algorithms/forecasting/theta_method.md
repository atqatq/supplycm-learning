---
title: "Theta Method | supplycm Algorithm Library"
description: "Plain-English explanation of theta_method from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, theta_method, supply chain, plain english, forecasting"
---

# Theta Method

> **Call it:** `from supplycm.forecasting import theta_method` · **Level:** Intermediate · **You need:** basic arithmetic only

A deceptively simple trick that wins forecasting competitions: split the series into two 'theta lines' - one exaggerating the long-term curve, one emphasizing short-term movement - combine their information, and extrapolate. Its accuracy-to-effort ratio is legendary.

**Think of it like this:** Two artists sketch the same face: one exaggerates the jawline, one the eyes - a curator blending both sketches captures the person better than either.

## When to reach for it

- A strong all-round baseline for regular demand series
- Competitions and benchmarks where simple must win

## Try it with supplycm

```python
from supplycm.forecasting import theta_method

result = theta_method([100, 112, 108, 125, 130, 128], theta=2.0, horizon=3)
print(result)
```

You should see something like:

```text
[138.2667, 144.2952, 150.3238]
```

Three forecasts combining trend persistence and short-term level - often beating far fancier models on real business data.

## Check yourself

1. What does theta = 2 do?
2. Why does such a simple method perform so well?
3. When would you NOT use it?

<details>
<summary>Show answers</summary>

1. It exaggerates the series' curvature in one decomposition line - amplifying the structure that plain lines average away.

2. It captures the two things business series actually have - gentle trend and recent level - without the flexibility to chase noise.

3. Strong multiplicative seasonality or intermittent demand - those need dedicated engines.

</details>

## Try this now

Run theta on a series where naive, SES, and Holt all trail it slightly; verify with MAE who wins.

---
[← Brown's Triple Exponential Smoothing](browns_triple_exponential.md) · [Back to Forecasting library](README.md) · [AR Model (Autoregressive) →](ar_model.md)
