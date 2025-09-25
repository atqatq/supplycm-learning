---
title: "Newsvendor Model | supplycm Algorithm Library"
description: "Plain-English explanation of newsvendor_model from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, newsvendor_model, supply chain, plain english, inventory"
---

# Newsvendor Model

> **Call it:** `from supplycm.inventory import newsvendor_model` · **Level:** Advanced · **You need:** basic arithmetic only

The newsvendor decides how many newspapers (or croissants, or phones) to stock for ONE selling season with uncertain demand: too many means leftovers, too few means missed sales. It weighs overage cost against underage cost and returns the order quantity that maximizes expected profit.

**Think of it like this:** A bakery's morning croissant bake: bake 200 and trash 30 unsold, or bake 120 and turn away 80 hungry customers - the model finds the bake that earns the most on average.

## When to reach for it

- Single-season or perishable ordering decisions
- Any one-shot commitment under demand uncertainty

## Try it with supplycm

```python
from supplycm.inventory import newsvendor_model

result = newsvendor_model(unit_cost=3, selling_price=6, salvage_value=1, demand_cdf=lambda q: min(max(q/200, 0), 1))
print(result)
```

You should see something like:

```text
120.0
```

An optimal order quantity near 120 for these economics - sell more than cost and salvage little, so the model leans slightly under the demand midpoint.

## Check yourself

1. What are overage and underage costs?
2. When should you order MORE than expected demand?
3. Fashion vs staples - who uses newsvendor more?

<details>
<summary>Show answers</summary>

1. Overage: cost minus salvage (what an unsold unit loses). Underage: price minus cost (what a missed sale loses).

2. When underage hurts more than overage - high margin items justify stocking past the average.

3. Fashion lives by it - one season, one shot; staples replenish repeatedly and use ongoing policies instead.

</details>

## Try this now

Compute the optimal order for cost 8, price 25, salvage 0 with a flat 0-300 demand CDF - explain why it exceeds the mean.

---
[← Decoupling Inventory](decoupling_inventory.md) · [Back to Inventory library](README.md) · [Marginal Analysis Newsvendor →](marginal_analysis_newsvendor.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
