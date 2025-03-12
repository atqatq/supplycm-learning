---
title: "Trend + Seasonal Forecast | supplycm Algorithm Library"
description: "Plain-English explanation of trend_seasonal_decomposition_forecast from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, trend_seasonal_decomposition_forecast, supply chain, plain english, demand planning"
---

# Trend + Seasonal Forecast

> **Call it:** `from supplycm.demand import trend_seasonal_decomposition_forecast` · **Level:** Intermediate · **You need:** basic arithmetic only

This splits history into trend (the slow direction) and season (the repeating wiggle), then puts them back together to forecast forward. It answers 'where are we heading, adjusted for the time of year?' - the workhorse question of demand planning.

**Think of it like this:** Hiking altitude: your overall climb (trend) plus the regular up-down of switchbacks (season) - you need both to know the next ledge.

## When to reach for it

- Products with steady growth AND yearly seasonality
- Explaining a forecast to management as 'trend plus the usual season'

## Try it with supplycm

```python
from supplycm.demand import trend_seasonal_decomposition_forecast

result = trend_seasonal_decomposition_forecast([100, 110, 130, 120, 115, 125, 150, 140, 130, 140, 170, 160], season_length=4, horizon=4)
print(result)
```

You should see something like:

```text
[153.0119, 162.9881, 182.9643, 177.6071]
```

The next 4 periods follow the upward trend dressed in the usual seasonal pattern - growth continues, but with familiar wiggles.

## Check yourself

1. What are the three ingredients of the forecast?
2. What breaks this method?
3. How would you sanity-check its output?

<details>
<summary>Show answers</summary>

1. Trend (long-run direction), seasonal indices (repeating pattern), and the combination applied to future periods.

2. Sudden level shifts - a new customer or lost contract - that history has never seen.

3. Compare against a simple baseline (last year same period); if the fancy method loses badly, distrust it.

</details>

## Try this now

Use 24 invented months with +2/month growth and a December x1.5 spike; forecast the next December and defend the number.

---
[← ABC-XYZ Demand Classification](demand_class_abc_xyz.md) · [Back to Demand Planning library](README.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
