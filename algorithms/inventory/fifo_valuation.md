---
title: "FIFO Valuation | supplycm Algorithm Library"
description: "Plain-English explanation of fifo_valuation from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, fifo_valuation, supply chain, plain english, inventory"
---

# FIFO Valuation

> **Call it:** `from supplycm.inventory import fifo_valuation` · **Level:** Intermediate · **You need:** basic arithmetic only

First-In-First-Out assumes the oldest stock sells first: each sale consumes the oldest cost layers, and what remains on the books is the freshest (usually highest) cost. FIFO matches physical reality for perishables and reports higher inventory value when prices rise.

**Think of it like this:** Drinking the oldest milk first: the fridge's contents are always the newest cartons you bought.

## When to reach for it

- Perishables and items with expiry discipline
- Financial reporting where ending inventory should reflect current costs

## Try it with supplycm

```python
from supplycm.inventory import fifo_valuation

result = fifo_valuation(layers=[(100, 10.0), (100, 12.0)], units_sold=150)
print(result)
```

You should see something like:

```text
[1600.0, [[50, 12.0]]]
```

Sold cost 1,550 (all 100 at 10 plus 50 at 12) and the remaining layers show on-hand value 600 - the newest cost stays in inventory.

## Check yourself

1. When prices RISE, which valuation shows higher profit - FIFO or LIFO?
2. Why does FIFO match physical flow for perishables?
3. What does FIFO leave on the balance sheet in inflationary times?

<details>
<summary>Show answers</summary>

1. FIFO - it charges older cheaper costs to sales, leaving higher (older-profit) margins on paper.

2. Because warehouses really do ship oldest first - valuation then mirrors the physical truth.

3. Inventory at recent, higher costs - balance sheet looks richer than LIFO's stale layers.

</details>

## Try this now

Sell 120 units from layers [(80, 5), (80, 7)] under FIFO by hand; verify cost of sales and ending value with the function.

---
[← Obsolescence Cost](obsolescence_cost.md) · [Back to Inventory library](README.md) · [LIFO Valuation →](lifo_valuation.md)
