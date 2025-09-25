---
title: "LIFO Valuation | supplycm Algorithm Library"
description: "Plain-English explanation of lifo_valuation from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, lifo_valuation, supply chain, plain english, inventory"
---

# LIFO Valuation

> **Call it:** `from supplycm.inventory import lifo_valuation` · **Level:** Advanced · **You need:** basic arithmetic only

Last-In-First-Out charges sales at the NEWEST costs, leaving old cost layers parked in inventory. In rising-price environments this raises cost of sales and lowers reported profit - and taxes. It matches 'replace what I sold' economics, though physical shelves rarely behave this way.

**Think of it like this:** You always claim the most recent grocery receipts as expenses, while the pantry's book value stays frozen years behind reality.

## When to reach for it

- Understanding tax-driven reporting choices in some countries
- Analyzing why a firm's inventory value looks suspiciously stale

## Try it with supplycm

```python
from supplycm.inventory import lifo_valuation

result = lifo_valuation(layers=[(100, 10.0), (100, 12.0)], units_sold=150)
print(result)
```

You should see something like:

```text
[1700.0, [[50, 10.0]]]
```

Sold cost 1,700 (newest first) and old layers remain - compare with FIFO's 1,550 to see the reporting gap inflation creates.

## Check yourself

1. Why does LIFO lower profit when prices rise?
2. Is LIFO allowed everywhere?
3. What is LIFO's dirty secret on the balance sheet?

<details>
<summary>Show answers</summary>

1. It charges today's expensive costs to sales while inventory stays at old cheap costs - bigger expense, smaller profit, lower tax.

2. No - IFRS bans it; it persists mainly under US GAAP.

3. Inventory values can be decades stale - a 'liquidation profit' hides inside if those layers ever sell.

</details>

## Try this now

Compute FIFO vs LIFO cost of sales for 200 units from layers [(150, 8), (150, 11)] and explain the 450 gap.

---
[← FIFO Valuation](fifo_valuation.md) · [Back to Inventory library](README.md) · [Weighted Average Cost →](weighted_average_cost.md)
