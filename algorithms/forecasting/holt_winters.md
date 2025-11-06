---
title: "Holt-Winters (Triple Smoothing) | supplycm Algorithm Library"
description: "Plain-English explanation of holt_winters from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, holt_winters, supply chain, plain english, forecasting"
---

# Holt-Winters (Triple Smoothing)

> **Call it:** `from supplycm.forecasting import holt_winters` · **Level:** Intermediate · **You need:** basic arithmetic only

Three engines in one: level (alpha), trend (beta), and season (gamma) - smoothed together and projected forward. It is the classic seasonal workhorse: it learns WHERE demand sits, WHERE it's heading, and the repeating wiggle, then combines all three.

**Think of it like this:** Forecasting a beach town's ice cream: the steady base (level), the growing tourism (trend), and the summer spike (season) - all at once.

## When to reach for it

- Seasonal products with enough history (2+ full seasons)
- Monthly demand with yearly patterns, weekly with day patterns

## Try it with supplycm

```python
from supplycm.forecasting import holt_winters

result = holt_winters([12, 14, 16, 30, 13, 15, 17, 32], alpha=0.5, beta=0.1, gamma=0.1, season_length=4)
print(result)
```

You should see something like:

```text
[[18.0, 0.0, 0.0, 0.0, 9.5, 14.725, 17.5512, 19.5368], [0.3125, 0.0, 0.0, 0.0, 0.95, 1.3775, 1.5224, 1.5687], [-6.0, -4.0, -2.0, 12.0, -5.05, -3.5725, -1.8551, 12.0463]]
```

Three component series return: the level hovers near 15, the trend inches up, and the seasonal component repeats the spike pattern - forecast = the trio combined.

## Check yourself

1. What do the three smoothing parameters tune?
2. Additive vs multiplicative seasonality - when each?
3. How much history does it need?

<details>
<summary>Show answers</summary>

1. Alpha: level speed; beta: trend speed; gamma: how quickly seasonal factors update.

2. Additive: spikes are a constant size (+20 every summer). Multiplicative: spikes scale with level (x1.5) - use multiplicative when seasons grow with the business.

3. At least two full seasons to learn a pattern and verify it repeats.

</details>

## Try this now

Forecast a full extra season for the example; then break gamma (0.9) and describe the nervous seasonality it produces.

---
[← Dampened Trend Method](dampened_trend.md) · [Back to Forecasting library](README.md) · [Doubling Seasonal Smoothing →](doubling_seasonal_smoothing.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
