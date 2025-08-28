---
title: "Quantity Discount Lot Sizing | supplycm Algorithm Library"
description: "Plain-English explanation of quantity_discount_mrp from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, quantity_discount_mrp, supply chain, plain english, mrp & production planning"
---

# Quantity Discount Lot Sizing

> **Call it:** `from supplycm.mrp import quantity_discount_mrp` · **Level:** Advanced · **You need:** basic arithmetic only

Suppliers drop the unit price at quantity breaks: 100+ units cost less each. This checks whether jumping UP to a break beats ordering exactly the need - saving unit cost but paying extra holding. It runs the comparison so you do not guess.

**Think of it like this:** Bulk-buying rice: the 10 kg bag costs less per kilo - worth it only if you actually finish it before it goes bad.

## When to reach for it

- Evaluating supplier price-break offers
- Deciding between exact-need orders and discount-sized ones

## Try it with supplycm

```python
from supplycm.mrp import quantity_discount_mrp

result = quantity_discount_mrp(net_requirements=[80, 20, 40], price_breaks=[100, 200])
print(result)
```

You should see something like:

```text
[100, 100, 100]
```

Order quantities snap to sensible break points where the math says it pays - and stay exact where the discount would be eaten by holding.

## Check yourself

1. What two costs fight when you take a discount?
2. Discount saves 2/unit on 120 extra units held one period, holding 1/unit/period. Take it?
3. When is chasing discounts a trap?

<details>
<summary>Show answers</summary>

1. Unit price saving vs extra holding cost of the bigger lot.

2. 2 x 120 = 240 saved vs 120 holding - yes, if the leftover truly sells next period.

3. When it distorts the whole plan - cash tied up, obsolescence risk, or the 'discount' applies to stuff you barely need.

</details>

## Try this now

For needs [60, 30] with breaks at 150, compare exact ordering vs break-jumping with holding 0.5/unit/period.

---
[← Order Multiples](order_multiples.md) · [Back to MRP & Production Planning library](README.md) · [Capacity Requirements Planning (CRP) →](capacity_requirements_planning.md)
