---
title: "Top-Down Reconciliation | supplycm Algorithm Library"
description: "Plain-English explanation of top_down_reconciliation from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, top_down_reconciliation, supply chain, plain english, forecasting"
---

# Top-Down Reconciliation

> **Call it:** `from supplycm.forecasting import top_down_reconciliation` · **Level:** Intermediate · **You need:** basic arithmetic only

You have one solid national forecast and messy product-level detail. Top-down splits the total by proportions - instant consistency between levels. The cost: product-level forecasts lose their own ups and downs, flattened into proportional slices.

**Think of it like this:** Splitting a team bonus by fixed percentages: the total is respected to the cent, but individual performance nuance vanishes.

## When to reach for it

- Aggregate forecasts are reliable; detail forecasts are noise
- Fast, consistent S&OP number sets

## Try it with supplycm

```python
from supplycm.forecasting import top_down_reconciliation

result = top_down_reconciliation(total_forecast=10000, proportions={'north': 0.4, 'south': 0.35, 'east': 0.25})
print(result)
```

You should see something like:

```text
{'north': 4000.0, 'south': 3500.0, 'east': 2500.0}
```

Regional forecasts that sum exactly to 10,000 - arithmetic guarantee, zero reconciliation meetings.

## Check yourself

1. What's the core trade-off vs bottom-up?
2. When do proportions mislead?
3. How often should proportions refresh?

<details>
<summary>Show answers</summary>

1. Consistency and noise reduction vs detail accuracy - top-down guarantees the sum but flattens local signal.

2. When the mix is shifting - new products, regional growth differences - stale proportions bake old reality into new numbers.

3. Regularly, from recent actual mix - proportions are a policy choice with a shelf life.

</details>

## Try this now

Reconcile 12,000 units across 4 regions with your proportions; deliberately shift one proportion and observe who gains.

---
[← Bates-Granger Forecast Combination](bates_granger_combination.md) · [Back to Forecasting library](README.md) · [Bottom-Up Reconciliation →](bottom_up_reconciliation.md)
