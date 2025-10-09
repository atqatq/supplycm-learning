---
title: "Lot-for-Lot (L4L) | supplycm Algorithm Library"
description: "Plain-English explanation of lot_for_lot from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, lot_for_lot, supply chain, plain english, inventory"
---

# Lot-for-Lot (L4L)

> **Call it:** `from supplycm.inventory import lot_for_lot` · **Level:** Beginner · **You need:** basic arithmetic only

Order exactly what each period needs - nothing more. Inventory never accumulates; every period with demand triggers its own order. It is the cleanest possible lot sizing and the baseline every cleverer rule must beat on total cost.

**Think of it like this:** Cooking exactly tonight's portion every night - zero leftovers, but you cook seven nights a week.

## When to reach for it

- Cheap setups and expensive holding (perishables, high-value items)
- The MRP default when order costs are negligible

## Try it with supplycm

```python
from supplycm.inventory import lot_for_lot

result = lot_for_lot(demands=[10, 0, 30, 20], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[0, 1, 2, 3], 400]
```

Orders of 10, 0, 30, 20 and the total cost - notice setups in every demand period, but inventory cost of nearly zero.

## Check yourself

1. What does L4L minimize and maximize?
2. When is L4L optimal in practice?
3. How does L4L interact with supplier MOQs?

<details>
<summary>Show answers</summary>

1. Minimizes holding; maximizes the NUMBER of setups - it trades storage for frequent ordering.

2. When setup cost is tiny - automated lines, digital ordering - or holding cost is huge.

3. Badly - small lots violate minimums; you then apply MOQ floors on top, which reintroduces inventory.

</details>

## Try this now

Compute L4L cost for [5, 60, 5, 60] with setup 50 and holding 2 - then argue whether bigger lots deserve a look.

---
[← Perishable Inventory Order](perishable_inventory.md) · [Back to Inventory library](README.md) · [Silver-Meal Heuristic →](silver_meal.md)
