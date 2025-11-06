---
title: "Classical Decomposition | supplycm Algorithm Library"
description: "Plain-English explanation of classical_decomposition from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, classical_decomposition, supply chain, plain english, forecasting"
---

# Classical Decomposition

> **Call it:** `from supplycm.forecasting import classical_decomposition` · **Level:** Intermediate · **You need:** basic arithmetic only

Split history into its three ingredients: trend (the slow drift), seasonal (the repeating wiggle), and residual (whatever is left). You see each piece separately - diagnose the trend, quantify the season, and inspect the leftovers for weirdness. Understanding first, forecasting second.

**Think of it like this:** A song split into bass line, melody, and hiss - you can finally hear which part is off-key.

## When to reach for it

- Explaining WHAT drives a series to management
- Checking seasonal shape before choosing a model

## Try it with supplycm

```python
from supplycm.forecasting import classical_decomposition

result = classical_decomposition([12, 14, 16, 30, 13, 15, 17, 32, 14, 16, 18, 34], season_length=4, multiplicative=False)
print(result)
```

You should see something like:

```text
[[None, None, 17.3, 17.9, 19.8, 19.8, 18.5, 19.1, 21.1, 22.8, None, None], [-6.5375, -5.3875, -0.9875, 12.9125, -6.5375, -5.3875, -0.9875, 12.9125, -6.5375, -5.3875, -0.9875, 12.9125], [None, None, -0.3125, -0.8125, -0.2625, 0.5875, -0.5125, -0.0125, -0.5625, -1.4125, None, None]]
```

Three lists: a gently rising trend, a repeating seasonal pattern peaking in period 4, and small residuals - a clean, explainable structure.

## Check yourself

1. What belongs in the residual component?
2. Additive vs multiplicative decomposition - how to choose?
3. Decomposition vs Holt-Winters - relationship?

<details>
<summary>Show answers</summary>

1. Everything unexplained: noise, promotions, one-off events - big residuals scream for investigation.

2. Additive if seasonal swings stay constant-sized; multiplicative if they scale with the level (bigger business, bigger swings).

3. Same three ingredients; decomposition explains them for diagnosis, Holt-Winters smooths and projects them for forecasting.

</details>

## Try this now

Decompose 12 quarters of invented data with a rising trend and Q4 spikes; label each component's story.

---
[← Doubling Seasonal Smoothing](doubling_seasonal_smoothing.md) · [Back to Forecasting library](README.md) · [MSTL Decomposition (Multiple Seasons) →](mstl_decomposition.md)
