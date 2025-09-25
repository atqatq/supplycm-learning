---
title: "Inventory Aging Schedule | supplycm Algorithm Library"
description: "Plain-English explanation of aging_schedule from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, aging_schedule, supply chain, plain english, inventory"
---

# Inventory Aging Schedule

> **Call it:** `from supplycm.inventory import aging_schedule` · **Level:** Intermediate · **You need:** basic arithmetic only

Groups inventory by how long it has been sitting: 0-30 days, 31-60, 61-90, 90+. Fresh stock moves, aging stock worries, ancient stock smells like markdowns. The schedule turns vague warehouse guilt into a per-bucket money table.

**Think of it like this:** A fridge audit by date labels: what's fresh, what needs eating this week, and the mystery container at the back.

## When to reach for it

- Monthly working-capital hygiene reviews
- Deciding markdown or clearance timing before value evaporates

## Try it with supplycm

```python
from supplycm.inventory import aging_schedule

result = aging_schedule(items=[('mug-A', 400.0, 15.0), ('mug-B', 250.0, 45.0), ('vase-old', 900.0, 95.0), ('plate', 600.0, 20.0)])
print(result)
```

You should see something like:

```text
{'0-30': 1000.0, '31-60': 250.0, '61-90': 0.0, '90+': 900.0}
```

Values bucketed by age - the 900-dollar vase sitting past 90 days is where your markdown conversation starts.

## Check yourself

1. Which bucket deserves attention first and why?
2. What causes inventory to age in the first place?
3. Is aging always the item's fault?

<details>
<summary>Show answers</summary>

1. The oldest - both because write-down risk peaks there and because it blocks space and cash.

2. Overbuying, forecast misses, slow movers nobody reviewed, and 'just in case' buys without expiry discipline.

3. No - bad slotting, lost items, and broken data also create ghost aging; verify physically before marking down.

</details>

## Try this now

Bucket 8 items by age; write one action per bucket (keep, promote, markdown, write-off).

---
[← GMROI (Gross Margin Return on Inventory)](gmroi.md) · [Back to Inventory library](README.md) · [Dead Stock Identification →](dead_stock_identification.md)
