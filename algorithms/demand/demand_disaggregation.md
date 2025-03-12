---
title: "Demand Disaggregation | supplycm Algorithm Library"
description: "Plain-English explanation of demand_disaggregation from the supplycm Demand Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, demand, demand_disaggregation, supply chain, plain english, demand planning"
---

# Demand Disaggregation

> **Call it:** `from supplycm.demand import demand_disaggregation` · **Level:** Beginner · **You need:** basic arithmetic only

Disaggregation is the reverse of aggregation: take one big forecast (say, '12,000 units next quarter for the family') and split it across products, regions, or customers using known proportions. The proportions can come from history, plans, or judgment.

**Think of it like this:** Cutting one big pizza into slices using each guest's usual appetite as the guide.

## When to reach for it

- Turning a brand-level forecast into SKU-level buying quantities
- Sharing a regional forecast across stores by their usual share

## Try it with supplycm

```python
from supplycm.demand import demand_disaggregation

result = demand_disaggregation(12000, {'small': 0.5, 'medium': 0.3, 'large': 0.2})
print(result)
```

You should see something like:

```text
{'small': 6000.0, 'medium': 3600.0, 'large': 2400.0}
```

The 12,000-unit family forecast becomes 6,000 / 3,600 / 2,400 per size - enough to place real purchase orders.

## Check yourself

1. Where do the proportions come from?
2. A new SKU has no history. How do you disaggregate to it?
3. Why not forecast each SKU directly?

<details>
<summary>Show answers</summary>

1. History (past sales shares), current plans (a size's push), or expert judgment - ideally a blend.

2. Borrow proportions from a similar existing product, then update as real sales arrive.

3. Family-level forecasts are more accurate; disaggregation keeps that accuracy while still producing SKU numbers.

</details>

## Try this now

Disaggregate 5,000 units across 3 stores with shares 0.4/0.35/0.25 and sanity-check the sums.

---
[← Demand Aggregation](demand_aggregation.md) · [Back to Demand Planning library](README.md) · [Seasonality Index →](seasonality_index.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
