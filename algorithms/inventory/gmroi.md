---
title: "GMROI (Gross Margin Return on Inventory) | supplycm Algorithm Library"
description: "Plain-English explanation of gmroi from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, gmroi, supply chain, plain english, inventory"
---

# GMROI (Gross Margin Return on Inventory)

> **Call it:** `from supplycm.inventory import gmroi` · **Level:** Intermediate · **You need:** basic arithmetic only

GMROI asks the retailer's favorite question: for every dollar tied up in inventory, how many dollars of gross margin do we earn back per year? Gross margin divided by average inventory cost. Above 1 you survive; healthy retailers run 2-4.

**Think of it like this:** Renting out rooms: GMROI is the yearly rent collected per dollar invested in furniture - some rooms earn their keep, some just take up space.

## When to reach for it

- Comparing categories with different margins and turns
- Deciding which product lines deserve more shelf and cash

## Try it with supplycm

```python
from supplycm.inventory import gmroi

result = gmroi(gross_margin=180000, avg_inventory_cost=90000)
print(result)
```

You should see something like:

```text
2.0
```

2.0 - every inventory dollar earns two back per year; a slow category at 0.8 is quietly eating the difference.

## Check yourself

1. Why is GMROI sharper than turnover alone?
2. Category A turns 10x at 20% margin, B turns 4x at 50% margin. Which wins?
3. How do you raise GMROI?

<details>
<summary>Show answers</summary>

1. Turnover ignores margin: cheap fast items can turn hugely and earn little; GMROI prices the actual profit per dollar of stock.

2. A earns 2.0 GMROI, B also 2.0 - identical return, very different operating styles.

3. Raise margin, raise turns, or cut the inventory base - usually a blend of all three beats any single push.

</details>

## Try this now

Compute GMROI for two invented categories and decide where next season's open-to-buy budget goes.

---
[← Inventory-to-Sales Ratio](inventory_to_sales_ratio.md) · [Back to Inventory library](README.md) · [Inventory Aging Schedule →](aging_schedule.md)
