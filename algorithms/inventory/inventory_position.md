---
title: "Inventory Position | supplycm Algorithm Library"
description: "Plain-English explanation of inventory_position from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, inventory_position, supply chain, plain english, inventory"
---

# Inventory Position

> **Call it:** `from supplycm.inventory import inventory_position` · **Level:** Beginner · **You need:** basic arithmetic only

Inventory position = on hand + on order - backorders. It is the number your reorder rules should watch: physical stock alone hides incoming receipts and promised units, which is how double-ordering (and starved promises) happen.

**Think of it like this:** Your real spendable balance: bank balance plus pending incoming transfers minus upcoming scheduled payments.

## When to reach for it

- Driving (s, Q) and (R, S) replenishment rules correctly
- Explaining to a colleague why 'we have 40 units' isn't the full story

## Try it with supplycm

```python
from supplycm.inventory import inventory_position

result = inventory_position(on_hand=40, on_order=100, backorders=20)
print(result)
```

You should see something like:

```text
120
```

120 - physical stock 40 misleads in both directions; position includes the 100 coming and the 20 already owed.

## Check yourself

1. Why must reorder rules watch position, not on-hand?
2. On hand 0, on order 500, position 500. Do you panic?
3. Backorders belong where in the arithmetic?

<details>
<summary>Show answers</summary>

1. Orders already placed will arrive - ignoring them double-orders; backorders owed must also be counted first.

2. Not necessarily - the pipeline is full; check ETAs and whether 500 covers lead-time demand.

3. They are subtracted - promises made must be served before 'available' means anything.

</details>

## Try this now

Compute position for three scenarios (heavy pipeline, heavy backorders, both) and decide which triggers an order.

---
[← ABC-XYZ Matrix](abc_xyz_matrix.md) · [Back to Inventory library](README.md) · [Days of Supply →](days_of_supply.md)
