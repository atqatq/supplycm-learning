---
title: "Doubling Seasonal Smoothing | supplycm Algorithm Library"
description: "Plain-English explanation of doubling_seasonal_smoothing from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, doubling_seasonal_smoothing, supply chain, plain english, forecasting"
---

# Doubling Seasonal Smoothing

> **Call it:** `from supplycm.forecasting import doubling_seasonal_smoothing` · **Level:** Advanced · **You need:** basic arithmetic only

An experimental variant that lets the seasonal pattern ADAPT at two time scales - capturing patterns that slowly shift or double in length. Niche, but a window into how seasonal smoothing generalizes when the calendar itself misbehaves.

**Think of it like this:** A surfer adjusting to waves that are gradually getting longer - riding a fixed rhythm fails when the ocean changes tempo.

## When to reach for it

- Unusual or evolving seasonal patterns
- Exploring how seasonal methods break and adapt

## Try it with supplycm

```python
from supplycm.forecasting import doubling_seasonal_smoothing

result = doubling_seasonal_smoothing([12, 14, 16, 30, 13, 15, 17, 32], alpha=0.3, beta=0.1, gamma=0.2, season_length=4, horizon=4)
print(result)
```

You should see something like:

```text
[14.088, 16.3582, 18.6504, 33.0997]
```

Seasonal estimates evolve across the horizon - compare with plain Holt-Winters to see where the adaptive version disagrees.

## Check yourself

1. When would a fixed season_length be wrong?
2. What is the practical risk of adaptive seasonality?
3. How would you validate it before trusting forecasts?

<details>
<summary>Show answers</summary>

1. Calendar drift, growing cycles, or data aggregated oddly - the true cycle no longer matches the assumed one.

2. Overfitting odd history - it can 'learn' patterns that were noise.

3. Hold out recent periods, compare against fixed-length Holt-Winters, and inspect the seasonal components for sanity.

</details>

## Try this now

Feed it 3 seasons where the spike grows each year; compare its next-season view with plain Holt-Winters.

---
[← Holt-Winters (Triple Smoothing)](holt_winters.md) · [Back to Forecasting library](README.md) · [Classical Decomposition →](classical_decomposition.md)
