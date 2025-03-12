---
title: "Promotional Demand Lift | supplycm Algorithm Library"
description: "Plain-English explanation of promotional_demand_lift from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, promotional_demand_lift, supply chain, plain english, demand planning"
---

# Promotional Demand Lift

> **Call it:** `from supplycm.demand import promotional_demand_lift` · **Level:** Beginner · **You need:** basic arithmetic only

Lift compares demand during a promotion with the normal baseline: 2.0 means sales doubled. Knowing lift lets you plan stock for the promo AND avoid polluting your baseline forecast with promo weeks. One number, two jobs.

**Think of it like this:** Measuring how much louder a concert is than the street noise - the lift is the extra volume the band adds.

## When to reach for it

- Sizing inventory ahead of a planned promotion
- Cleaning promo weeks out of the baseline before fitting forecast models

## Try it with supplycm

```python
from supplycm.demand import promotional_demand_lift

result = promotional_demand_lift(baseline_demand=100, promotion_demand=260)
print(result)
```

You should see something like:

```text
2.6
```

Lift of 1.6 - the promotion added 60% on top of baseline; order and staff for that multiplier.

## Check yourself

1. Why exclude promo weeks from the baseline forecast?
2. Lift was 1.8 last time; order for 1.8 this time?
3. After the promo ends, what often happens to demand?

<details>
<summary>Show answers</summary>

1. Otherwise the model 'learns' the promo spike as normal and over-forecasts quiet weeks.

2. Careful - lift depends on discount depth, season, and fatigue. Use history as a guide, then adjust for what's different.

3. A dip - customers stocked up (pantry effect). Plan the trough, not just the peak.

</details>

## Try this now

Given baseline 80 and a promo week of 200, compute lift; then forecast the post-promo week assuming a 20% pantry dip.

---
[← Seasonality Index](seasonality_index.md) · [Back to Demand Planning library](README.md) · [Cannibalization Effect →](cannibalization_effect.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
