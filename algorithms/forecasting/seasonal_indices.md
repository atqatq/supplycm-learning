---
title: "Seasonal Indices | supplycm Algorithm Library"
description: "Plain-English explanation of seasonal_indices from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, seasonal_indices, supply chain, plain english, forecasting"
---

# Seasonal Indices

> **Call it:** `from supplycm.forecasting import seasonal_indices` · **Level:** Beginner · **You need:** basic arithmetic only

Boils the repeating pattern into one number per season position: 1.0 is average, 1.3 means 30% above typical, 0.7 means 30% below. Compute once, reuse everywhere - deseasonalize history, seasonalize any level forecast, explain December to the board.

**Think of it like this:** A restaurant's hourly rush table: 11am is 0.4, 1pm is 1.6 - staffing becomes arithmetic.

## When to reach for it

- Planning seasonal staffing, stock, and promotions
- Deseasonalizing data before fitting trend models

## Try it with supplycm

```python
from supplycm.forecasting import seasonal_indices

result = seasonal_indices([100, 105, 110, 320, 102, 107, 112, 330], season_length=4)
print(result)
```

You should see something like:

```text
[0.6582, 0.534, 0.7233, 2.0844]
```

Four indices repeat: the fourth position sits far above 1.0 - that's your spike, quantified for every future cycle.

## Check yourself

1. What should the four indices average out to?
2. How do you deseasonalize a series?
3. One crazy December skews the December index. Fix?

<details>
<summary>Show answers</summary>

1. About 1.0 - they are shares of the average period, and shares must balance.

2. Divide each actual by its position's index - what remains shows the true trend without the wiggle.

3. Compute indices over multiple years, or cap/dampen the outlier's influence before averaging.

</details>

## Try this now

Compute 12 monthly indices from 3 years of invented data with a December x1.6 peak; deseasonalize and describe the trend.

---
[← STL (Seasonal-Trend Loess)](seasonal_trend_loess.md) · [Back to Forecasting library](README.md) · [Croston's Method →](crostons_method.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
