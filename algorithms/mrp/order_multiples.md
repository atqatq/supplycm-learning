---
title: "Order Multiples | supplycm Algorithm Library"
description: "Plain-English explanation of order_multiples from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, order_multiples, supply chain, plain english, mrp & production planning"
---

# Order Multiples

> **Call it:** `from supplycm.mrp import order_multiples` · **Level:** Beginner · **You need:** basic arithmetic only

Many items ship in packs: 12 per box, 50 per pallet. Order multiples round every order UP to a whole number of packs. It keeps suppliers, warehouses, and forklifts happy - the arithmetic is tiny but the operational peace is real.

**Think of it like this:** Buying beer: you cannot order 7 bottles - it comes in six-packs, so you take 12.

## When to reach for it

- Items bought in cases, boxes, or pallet quantities
- Cleaning up MRP outputs before sending POs

## Try it with supplycm

```python
from supplycm.mrp import order_multiples

result = order_multiples(order_qty=70, multiple=24)
print(result)
```

You should see something like:

```text
72
```

72 - rounded up to three full boxes of 24; the supplier ships clean packs and nobody repacks in the warehouse.

## Check yourself

1. Round up or down to the multiple?
2. Order 24 with multiple 24 - any change?
3. Multiple 100 on an item needing 5/year. Problem?

<details>
<summary>Show answers</summary>

1. Up - rounding down would violate the requirement; the small excess becomes inventory.

2. None - it is already a whole multiple.

3. Huge - the multiple forces 20x the annual need; renegotiate pack size or find another supplier.

</details>

## Try this now

Round [30, 55, 12] to multiples of 12; compute total excess units purchased.

---
[← Maximum Order Quantity (MaxOQ)](maximum_order_quantity.md) · [Back to MRP & Production Planning library](README.md) · [Quantity Discount Lot Sizing →](quantity_discount_mrp.md)
