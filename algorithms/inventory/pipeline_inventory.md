---
title: "Pipeline Inventory | supplycm Algorithm Library"
description: "Plain-English explanation of pipeline_inventory from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, pipeline_inventory, supply chain, plain english, inventory"
---

# Pipeline Inventory

> **Call it:** `from supplycm.inventory import pipeline_inventory` · **Level:** Beginner · **You need:** basic arithmetic only

Pipeline inventory is stock in transit - ordered, paid for maybe, but sitting on trucks, ships, or trains. It equals demand rate times transit time. Longer supply chains quietly grow this number, and it is cash you cannot touch or sell.

**Think of it like this:** The groceries in the delivery van: bought, yours on paper, useless for tonight's dinner.

## When to reach for it

- Counting true inventory investment in long supply chains
- Evaluating sourcing changes (nearshoring cuts the pipeline)

## Try it with supplycm

```python
from supplycm.inventory import pipeline_inventory

result = pipeline_inventory(demand_rate=50, transit_time=21)
print(result)
```

You should see something like:

```text
1050
```

1,050 units always afloat - over a million dollars' worth if units cost 100; that is what 3 weeks of ocean buys you.

## Check yourself

1. Why is pipeline inventory 'invisible' in warehouses?
2. A supplier switches from sea (30 days) to air (3 days). Pipeline effect?
3. Who 'owns' pipeline stock financially?

<details>
<summary>Show answers</summary>

1. It sits on vehicles, not shelves - it never shows in stock counts but always shows in working capital.

2. Drops by 27 days of demand - at 50/day, 1,350 fewer units afloat; air freight prices must beat that saving.

3. Depends on Incoterms - FOB vs DDP decides whose balance sheet carries the floating cash.

</details>

## Try this now

Compute pipeline stock for 200/day demand and 40-day transit; convert to cash at unit cost 25 and gasp appropriately.

---
[← Bullwhip Effect Ratio](bullwhip_effect.md) · [Back to Inventory library](README.md) · [Anticipation Inventory →](anticipation_inventory.md)
