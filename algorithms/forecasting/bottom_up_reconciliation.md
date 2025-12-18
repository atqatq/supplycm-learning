---
title: "Bottom-Up Reconciliation | supplycm Algorithm Library"
description: "Plain-English explanation of bottom_up_reconciliation from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, bottom_up_reconciliation, supply chain, plain english, forecasting"
---

# Bottom-Up Reconciliation

> **Call it:** `from supplycm.forecasting import bottom_up_reconciliation` · **Level:** Intermediate · **You need:** basic arithmetic only

The opposite route: trust the detailed forecasts and SUM them upward. Every product's story survives; the total inherits all their errors and inconsistencies. Right when local detail is rich and reliable - wrong when each detail forecast is mostly noise.

**Think of it like this:** Adding up everyone's individual travel estimates for the group trip - respectful of each detail, but the total inherits every optimism and every typo.

## When to reach for it

- Detail forecasts are individually reliable
- Category plans that must reflect SKU-specific realities

## Try it with supplycm

```python
from supplycm.forecasting import bottom_up_reconciliation

result = bottom_up_reconciliation(bottom_level_forecasts={'skuA': 300, 'skuB': 450, 'skuC': 250}, hierarchy={'family1': ['skuA', 'skuB', 'skuC']})
print(result)
```

You should see something like:

```text
{'skuA': 300, 'skuB': 450, 'skuC': 250, 'family1': 1000}
```

Family totals computed from the leaves - 1,000 for family1, built from its SKUs' own forecasts.

## Check yourself

1. What does bottom-up preserve that top-down destroys?
2. Why can the bottom-up total be less accurate than its parts?
3. What's the middle path?

<details>
<summary>Show answers</summary>

1. SKU-level signal - real product stories survive the aggregation.

2. Unbiased errors ADD in aggregation - the total carries the sum of everyone's noise; top-down would have imposed calm.

3. Middle-out or optimized reconciliation - reconcile both directions with weights; modern tools blend instead of choosing.

</details>

## Try this now

Reconcile 6 SKUs into 2 families bottom-up; then force the family total to a target and redistribute - compare the pain.

---
[← Top-Down Reconciliation](top_down_reconciliation.md) · [Back to Forecasting library](README.md) · [Tracking Signal →](tracking_signal.md)
