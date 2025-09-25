---
title: "Inventory Turnover Ratio | supplycm Algorithm Library"
description: "Plain-English explanation of inventory_turnover_ratio from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, inventory_turnover_ratio, supply chain, plain english, inventory"
---

# Inventory Turnover Ratio

> **Call it:** `from supplycm.inventory import inventory_turnover_ratio` · **Level:** Beginner · **You need:** basic arithmetic only

How many times per year does your inventory sell through completely? Cost of goods sold divided by average inventory. Turning 6 times a year means stock sits about two months; turning 12 means a month. Higher is usually leaner - until it starts costing stockouts.

**Think of it like this:** How many times a year your fridge empties and refills - a busy household turns over fast; a holiday home fridge barely turns at all.

## When to reach for it

- Benchmarking operational efficiency year over year
- Comparing your performance against industry standards

## Try it with supplycm

```python
from supplycm.inventory import inventory_turnover_ratio

result = inventory_turnover_ratio(cogs=600000, avg_inventory=100000)
print(result)
```

You should see something like:

```text
6.0
```

6 turns a year - about 61 days of inventory on average; run the same numbers on a best-in-class competitor for a humbling comparison.

## Check yourself

1. Why use COGS and not sales revenue in the numerator?
2. Is higher turnover always better?
3. Turnover falls from 8 to 6. First suspects?

<details>
<summary>Show answers</summary>

1. Inventory is valued at cost, not retail - mixing cost and revenue inflates the ratio dishonestly.

2. No - past a point you stock out, expedite, and lose sales; the goal is the best total cost, not the biggest number.

3. Slower sales, a big buy ahead of a price rise, dead stock accumulating - or simply bad purchasing timing.

</details>

## Try this now

Compute turnover for a business with COGS 1.2M and average stock 300k; state its months of supply.

---
[← Days of Supply](days_of_supply.md) · [Back to Inventory library](README.md) · [Inventory-to-Sales Ratio →](inventory_to_sales_ratio.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
