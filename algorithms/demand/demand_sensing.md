---
title: "Demand Sensing | supplycm Algorithm Library"
description: "Plain-English explanation of demand_sensing from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, demand_sensing, supply chain, plain english, demand planning"
---

# Demand Sensing

> **Call it:** `from supplycm.demand import demand_sensing` · **Level:** Intermediate · **You need:** basic arithmetic only

Sensing blends a statistical forecast with the freshest actuals to correct course mid-period. If the first week of the month ran hot, the rest of the month's forecast gets nudged up immediately, instead of waiting for next month's re-plan.

**Think of it like this:** A GPS rerouting mid-drive because of traffic ahead - the destination is unchanged, the path adapts now.

## When to reach for it

- Short-shelf-life goods (bakery, fresh food) where being wrong for a week is waste
- E-commerce with fast signal (daily sales) and fast response (daily replenishment)

## Try it with supplycm

```python
from supplycm.demand import demand_sensing

result = demand_sensing(forecast=[100, 100, 100, 100], actual_recent=[115, 112, 118], adjustment_window=3)
print(result)
```

You should see something like:

```text
[115.0, 115.0, 115.0, 115.0]
```

Recent actuals run above plan, so the remaining weeks get lifted toward the fresh signal - the forecast self-corrects within the month.

## Check yourself

1. What powers demand sensing?
2. Sensing vs just re-forecasting weekly - difference?
3. When does sensing add the most value?

<details>
<summary>Show answers</summary>

1. Very recent actuals (POS, e-commerce) that arrive faster than the standard monthly re-forecast.

2. Sensing makes small guided adjustments to the existing forecast; re-forecasting rebuilds it from scratch and can swing wildly.

3. When reaction is possible - you can actually change production or shipments inside the period.

</details>

## Try this now

Take a flat 4-week forecast, pretend week 1 ran 20% hot, and sense-correct the remaining weeks by hand before using the function.

---
[← Stockout Demand Loss](stockout_demand_loss.md) · [Back to Demand Planning library](README.md) · [ABC-XYZ Demand Classification →](demand_class_abc_xyz.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
