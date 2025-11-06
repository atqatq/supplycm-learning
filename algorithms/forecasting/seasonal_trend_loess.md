---
title: "STL (Seasonal-Trend Loess) | supplycm Algorithm Library"
description: "Plain-English explanation of seasonal_trend_loess from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, seasonal_trend_loess, supply chain, plain english, forecasting"
---

# STL (Seasonal-Trend Loess)

> **Call it:** `from supplycm.forecasting import seasonal_trend_loess` · **Level:** Advanced · **You need:** basic arithmetic only

STL is the artisan version of decomposition: it fits trend and season with local, flexible smoothing (LOESS) instead of rigid averages. The seasonal shape may evolve, the trend may bend - STL follows gracefully and handles outliers better than classical methods.

**Think of it like this:** Tailoring vs off-the-rack: classical decomposition is a fixed size; STL measures and stitches to fit the actual body.

## When to reach for it

- Series whose seasonal shape changes over time
- Publication-quality decomposition with robust behavior

## Try it with supplycm

```python
from supplycm.forecasting import seasonal_trend_loess

result = seasonal_trend_loess([12, 14, 16, 30, 13, 15, 17, 32, 14, 16, 18, 34], season_length=4)
print(result)
```

You should see something like:

```text
[[17.0, 17.0, 17.0, 17.6, 18.2, 21.4, 18.2, 18.8, 19.4, 22.8, 22.8, 22.8], [-5.0333, -5.2333, -2.1667, 12.4333, -5.0333, -5.2333, -2.1667, 12.4333, -5.0333, -5.2333, -2.1667, 12.4333], [0.0333, 2.2333, 1.1667, -0.0333, -0.1667, -1.1667, 0.9667, 0.7667, -0.3667, -1.5667, -2.6333, -1.2333]]
```

Trend, seasonal, residual return - notice the smooth, flexible trend and a seasonal shape free to drift slightly across cycles.

## Check yourself

1. What does 'local smoothing' (LOESS) actually do?
2. When is STL worth it over classical decomposition?
3. What does STL NOT give you?

<details>
<summary>Show answers</summary>

1. Fits small flexible curves over local neighborhoods - capturing bends and drifts rigid methods must average away.

2. When the pattern evolves, the trend bends, or outliers plague the data - flexibility earns its keep.

3. A forecast by itself - it explains structure; pair it with forecasting the extracted components.

</details>

## Try this now

Decompose a series whose seasonal spike grows each year; show how STL tracks the growth classical misses.

---
[← MSTL Decomposition (Multiple Seasons)](mstl_decomposition.md) · [Back to Forecasting library](README.md) · [Seasonal Indices →](seasonal_indices.md)
