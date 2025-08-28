---
title: "Minimum Order Quantity (MOQ) | supplycm Algorithm Library"
description: "Plain-English explanation of minimum_order_quantity from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, minimum_order_quantity, supply chain, plain english, mrp & production planning"
---

# Minimum Order Quantity (MOQ)

> **Call it:** `from supplycm.mrp import minimum_order_quantity` · **Level:** Beginner · **You need:** basic arithmetic only

Suppliers set minimums: 'at least 100 units or we cannot ship'. MOQ lifts small requirements up to that floor. It protects the supplier's economics - and quietly creates inventory when your real need is smaller.

**Think of it like this:** Delivery apps' minimum order: you wanted a 6-dollar snack, you're getting 15 dollars of food.

## When to reach for it

- Applying supplier contract minimums to MRP outputs
- Explaining to planners why small needs become big orders

## Try it with supplycm

```python
from supplycm.mrp import minimum_order_quantity

result = minimum_order_quantity(net_requirements=[10, 30, 0, 90], min_qty=50)
print(result)
```

You should see something like:

```text
[50, 50, 0, 90]
```

10 becomes 50 and 30 becomes 50; 90 passes through - every requirement below the floor gets rounded UP to it.

## Check yourself

1. What does MOQ do to inventory when demand is small?
2. Requirement is 49, MOQ is 50. Order how much?
3. How can buyers fight bad MOQ effects?

<details>
<summary>Show answers</summary>

1. Inflates it - you hold the difference between floor and need until it is consumed.

2. 50 - just under the floor still triggers the floor.

3. Negotiate lower minimums, mix SKUs on one PO, or hold supplier-managed stock nearby.

</details>

## Try this now

Apply MOQ 100 to [5, 120, 80, 0] and compute the total excess units ordered above true need.

---
[← Economic Part Period (EPP) Lot Sizing](lot_size_rule_epr.md) · [Back to MRP & Production Planning library](README.md) · [Maximum Order Quantity (MaxOQ) →](maximum_order_quantity.md)
