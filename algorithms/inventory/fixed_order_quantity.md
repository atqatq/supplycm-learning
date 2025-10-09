---
title: "Fixed Order Quantity Lot Sizing | supplycm Algorithm Library"
description: "Plain-English explanation of fixed_order_quantity from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, fixed_order_quantity, supply chain, plain english, inventory"
---

# Fixed Order Quantity Lot Sizing

> **Call it:** `from supplycm.inventory import fixed_order_quantity` · **Level:** Intermediate · **You need:** basic arithmetic only

Order the same fixed quantity whenever stock runs low - the replenishment rhythm of every two-bin system and vending machine. Simplicity itself for the floor; the cost is rounding: demand gets covered, but not elegantly.

**Think of it like this:** A water cooler: whenever the bottle empties, you swap in the same 19-liter bottle - nobody recalculates anything.

## When to reach for it

- Systems without software (kanban racks, two-bin shelves)
- Processes with natural fixed batches (trucks, molds, ovens)

## Try it with supplycm

```python
from supplycm.inventory import fixed_order_quantity

result = fixed_order_quantity(demands=[10, 20, 30, 40], fixed_q=50, setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[[0, 50], [2, 50]], 300.0]
```

The (period, quantity) order list and total cost - orders fire when cumulative demand drains the stock, always in chunks of 50.

## Check yourself

1. What triggers each order under this rule?
2. Fixed Q of 50 on tiny demands - what accumulates?
3. Where does this rule shine despite inefficiency?

<details>
<summary>Show answers</summary>

1. Inventory position falling below what's needed - the rule then fires one fixed chunk.

2. Inventory - rounding up small needs means stock sits longer; holding cost quietly grows.

3. Robustness - no data needed beyond 'bin empty', which is why it survives on real shop floors.

</details>

## Try this now

Simulate fixed Q=40 over the example demands; mark which periods hold avoidable stock.

---
[← Wagner-Whitin (Optimal Lot Sizing)](wagner_whitin.md) · [Back to Inventory library](README.md) · [Periodic Review (R, S) Policy →](periodic_review_policy.md)
