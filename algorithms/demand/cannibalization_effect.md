---
title: "Cannibalization Effect | supplycm Algorithm Library"
description: "Plain-English explanation of cannibalization_effect from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, cannibalization_effect, supply chain, plain english, demand planning"
---

# Cannibalization Effect

> **Call it:** `from supplycm.demand import cannibalization_effect` · **Level:** Intermediate · **You need:** basic arithmetic only

When a new product steals sales from your own existing one, that steal is cannibalization. The function measures how much of the new product's sales came at the old product's expense. Missing this effect leads you to double-count demand and over-order both.

**Think of it like this:** Opening a second lemonade stand across the street from your first one - total sales grow less than the new stand suggests.

## When to reach for it

- Launching a variant (new flavor, new model) of an existing product
- Estimating the TRUE incremental volume of a line extension

## Try it with supplycm

```python
from supplycm.demand import cannibalization_effect

result = cannibalization_effect(existing_before=500, existing_after=380, new_product_sales=200)
print(result)
```

You should see something like:

```text
0.6
```

The old product lost 120 units that went to the new one - the genuinely NEW demand is only 80, not 200.

## Check yourself

1. New product sells 200; old product fell 120. Net new demand?
2. Why does cannibalization inflate inventory risk?
3. Name a launch with low cannibalization risk.

<details>
<summary>Show answers</summary>

1. 80 units - the 120 that just moved between your own products.

2. You order for 200 new units, but total demand grew only 80 - the extra 120 become slow stock on both lines.

3. A genuinely new use case or new customer segment - e.g., a bike shop adding e-bikes for commuters who never bought bikes before.

</details>

## Try this now

A shop sells 300 classic tees; after launching a graphic tee that sells 150, classics fall to 240. Compute net new demand.

---
[← Promotional Demand Lift](promotional_demand_lift.md) · [Back to Demand Planning library](README.md) · [Stockout Demand Loss →](stockout_demand_loss.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
