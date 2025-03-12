---
title: "Seasonality Index | supplycm Algorithm Library"
description: "Plain-English explanation of seasonality_index from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, seasonality_index, supply chain, plain english, demand planning"
---

# Seasonality Index

> **Call it:** `from supplycm.demand import seasonality_index` · **Level:** Beginner · **You need:** basic arithmetic only

A seasonality index tells you how each period compares to the average: 1.0 is ordinary, 1.3 means 30% above typical, 0.7 means 30% below. Compute it from history, then apply it to any level forecast to get a seasonal forecast. This is the heart of seasonal planning.

**Think of it like this:** Restaurant rush hours: Saturday is 1.4, Monday is 0.6 - staff and stock accordingly.

## When to reach for it

- Planning holiday peaks (toy store in December, bakery on weekends)
- Deseasonalizing history so you can see the true trend underneath

## Try it with supplycm

```python
from supplycm.demand import seasonality_index

result = seasonality_index([120, 110, 100, 90, 95, 105, 150, 160, 155, 145, 140, 130], season_length=12)
print(result)
```

You should see something like:

```text
[0.96, 0.88, 0.8, 0.72, 0.76, 0.84, 1.2, 1.28, 1.24, 1.16, 1.12, 1.04]
```

Mid-year months sit below 1.0 while month 7 jumps above 1.0 - the summer peak is now a number you can plan with.

> **Watch out:** Indices are only as good as the history - one unusual year (a strike, a lockdown) distorts them.

## Check yourself

1. What does an index of 1.25 for December mean?
2. How do you deseasonalize?
3. Demand has two peaks a year. What season length fits?

<details>
<summary>Show answers</summary>

1. December typically runs 25% above the average month.

2. Divide each actual by its period's index - what remains is the underlying level and trend.

3. Half a year per cycle - use season_length 6 (or 26 weekly periods per half-year cycle).

</details>

## Try this now

Compute 12 monthly indices from invented data with a December peak, then forecast next December from an average of 1,000.

---
[← Demand Disaggregation](demand_disaggregation.md) · [Back to Demand Planning library](README.md) · [Promotional Demand Lift →](promotional_demand_lift.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
