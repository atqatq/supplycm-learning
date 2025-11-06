---
title: "MSTL Decomposition (Multiple Seasons) | supplycm Algorithm Library"
description: "Plain-English explanation of mstl_decomposition from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, mstl_decomposition, supply chain, plain english, forecasting"
---

# MSTL Decomposition (Multiple Seasons)

> **Call it:** `from supplycm.forecasting import mstl_decomposition` · **Level:** Advanced · **You need:** basic arithmetic only

Real series often have MORE than one season: hourly data has daily AND weekly rhythms. MSTL iteratively peels off multiple seasonal layers at the lengths you specify, leaving trend plus remainder. One function, several calendars.

**Think of it like this:** Untangling headphones with two knots instead of one - remove each loop separately and the cable finally runs free.

## When to reach for it

- Hourly/daily retail or energy data with nested cycles
- Any series where one season_length clearly isn't enough

## Try it with supplycm

```python
from supplycm.forecasting import mstl_decomposition

result = mstl_decomposition([10, 20, 15, 12, 22, 17, 14, 24, 19, 16, 26, 21], seasonal_periods=[4])
print(result)
```

You should see something like:

```text
[[0.0, 0.0, 0.0, -0.0, -0.0, 0.0, 0.0, 0.0, -0.0, 0.0, 0.0, 0.0], [[-0.85, -1.25, 0.75, 1.35, -0.85, -1.25, 0.75, 1.35, -0.85, -1.25, 0.75, 1.35]], [10.85, 21.25, 14.25, 10.65, 22.85, 18.25, 13.25, 22.65, 19.85, 17.25, 25.25, 19.65]]
```

Trend, one or more seasonal layers, and the remainder return separately - each seasonal layer accounts for its own rhythm.

## Check yourself

1. When do multiple seasonalities coexist?
2. What breaks classical decomposition that MSTL handles?
3. How do you choose the seasonal periods?

<details>
<summary>Show answers</summary>

1. High-frequency operations: daily pattern within weekly pattern within yearly pattern - each calendar leaves its fingerprint.

2. Classical handles ONE season length; layered cycles contaminate its single seasonal estimate.

3. From the data's clock: 24 and 168 for hourly (day/week), 7 and 365 for daily - use the cycles your business actually repeats.

</details>

## Try this now

Generate 28 days of data with both a 4-period and an 8-period cycle; let MSTL separate them and verify each layer.

---
[← Classical Decomposition](classical_decomposition.md) · [Back to Forecasting library](README.md) · [STL (Seasonal-Trend Loess) →](seasonal_trend_loess.md)
