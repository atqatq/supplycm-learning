---
title: "EOQ with Backorders | supplycm Algorithm Library"
description: "Plain-English explanation of eoq_with_backorders from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, eoq_with_backorders, supply chain, plain english, inventory"
---

# EOQ with Backorders

> **Call it:** `from supplycm.inventory import eoq_with_backorders` · **Level:** Advanced · **You need:** basic arithmetic only

Allowing backorders changes the EOQ math: some demand waits instead of being filled from stock, so peak inventory drops and holding costs fall - at the price of a shortage cost per unit-year of waiting. The function finds the order size that balances all three costs.

**Think of it like this:** A barber who books you for next week instead of a walk-in queue: fewer chairs needed, some customers grumble - balanced correctly, everyone wins.

## When to reach for it

- Items where customers WILL wait (spare parts with contracts, B2B)
- Squeezing cost when holding is expensive and stockouts are tolerable

## Try it with supplycm

```python
from supplycm.inventory import eoq_with_backorders

result = eoq_with_backorders(demand=1200, ordering_cost=50, holding_cost=2, shortage_cost=8)
print(result)
```

You should see something like:

```text
273.8613
```

A larger order quantity with planned short periods - the math confirms that letting some demand wait saves more in holding than it costs in goodwill.

## Check yourself

1. What new cost enters the EOQ picture?
2. Shortage cost is very high. What does the model do?
3. How is this different from just accepting lost sales?

<details>
<summary>Show answers</summary>

1. Shortage/backorder cost - the penalty for making customers wait per unit and per time.

2. Almost no backorders allowed - it converges back to plain EOQ behavior.

3. Backordered customers are LOST SALES that came back - demand is delayed, not destroyed.

</details>

## Try this now

Recompute with shortage_cost=3 vs 30 and explain how the planned stockout portion reacts.

---
[← Economic Production Quantity (EPQ)](economic_production_quantity.md) · [Back to Inventory library](README.md) · [EOQ with Quantity Discounts →](eoq_quantity_discount.md)
