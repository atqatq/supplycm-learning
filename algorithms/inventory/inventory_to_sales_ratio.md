---
title: "Inventory-to-Sales Ratio | supplycm Algorithm Library"
description: "Plain-English explanation of inventory_to_sales_ratio from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, inventory_to_sales_ratio, supply chain, plain english, inventory"
---

# Inventory-to-Sales Ratio

> **Call it:** `from supplycm.inventory import inventory_to_sales_ratio` · **Level:** Beginner · **You need:** basic arithmetic only

Inventory value divided by sales value for the same period - a quick 'are we carrying too much relative to business volume?' gauge. Rising ratio with flat sales is a classic early warning: stock is growing faster than the business.

**Think of it like this:** Checking whether your pantry grows faster than your appetite - the ratio, not the absolute size, is the tell.

## When to reach for it

- Executive dashboards tracking working capital drift
- Comparing subsidiaries or periods at different scales

## Try it with supplycm

```python
from supplycm.inventory import inventory_to_sales_ratio

result = inventory_to_sales_ratio(inventory_value=250000, sales_value=1000000)
print(result)
```

You should see something like:

```text
0.25
```

0.25 - you hold a quarter of a year's sales in stock; watch this number monthly and ask why whenever it climbs.

## Check yourself

1. How does this differ from turnover?
2. Ratio rises 0.22 to 0.31 while sales are flat. Interpretations?
3. Is a rising ratio ever GOOD?

<details>
<summary>Show answers</summary>

1. They are mirror images: turnover is sales/inventory (times per year); this ratio is inventory/sales (fraction of a year).

2. Over-buying, slowing demand, or strategic stock for a known event - verify which before acting.

3. Yes - deliberate pre-builds, supplier price locks, or new product launches can justify it; the ratio asks the question, the plan answers it.

</details>

## Try this now

Track a fictional company's ratio across 6 quarters where one quarter has a deliberate pre-build - tell the story.

---
[← Inventory Turnover Ratio](inventory_turnover_ratio.md) · [Back to Inventory library](README.md) · [GMROI (Gross Margin Return on Inventory) →](gmroi.md)
