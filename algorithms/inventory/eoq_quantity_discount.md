---
title: "EOQ with Quantity Discounts | supplycm Algorithm Library"
description: "Plain-English explanation of eoq_quantity_discount from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, eoq_quantity_discount, supply chain, plain english, inventory"
---

# EOQ with Quantity Discounts

> **Call it:** `from supplycm.inventory import eoq_quantity_discount` · **Level:** Intermediate · **You need:** basic arithmetic only

Suppliers offer lower unit prices at bigger quantities. This checks each price break: compute the EOQ at that price, and if the break requires ordering more, weigh the unit savings against extra holding. The output is the cheapest total-cost quantity, not the biggest discount.

**Think of it like this:** Bulk-buying rice: the 10 kg bag costs less per kilo - worth it only if the savings beat the cost of storing extra rice.

## When to reach for it

- Evaluating supplier price-break offers on steady items
- Deciding between exact-need ordering and discount-chasing

## Try it with supplycm

```python
from supplycm.inventory import eoq_quantity_discount

result = eoq_quantity_discount(demand=1200, ordering_cost=50, holding_rate=0.25, discounts=[(300, 9.5), (600, 9.0)])
print(result)
```

You should see something like:

```text
[40.0, 363000.0]
```

The best order quantity and its total annual cost - notice when jumping to a break pays and when holding eats the discount alive.

## Check yourself

1. Why not always take the biggest discount?
2. Discount at 600 units, EOQ is 245. Compare what?
3. What if holding cost is tiny (fast-moving cheap item)?

<details>
<summary>Show answers</summary>

1. Holding extra stock costs 25%+ per year - the discount must beat the storage bill, not just look bigger per unit.

2. Total annual cost at 245 (higher price) vs at 600 (discount price) - the function runs both sides of that argument.

3. Discounts become attractive more often - less capital sits idle per extra unit.

</details>

## Try this now

Test discounts [(200, 8.5)] against base price 10 for demand 600, ordering 30, holding rate 0.3 - take the break or not?

---
[← EOQ with Backorders](eoq_with_backorders.md) · [Back to Inventory library](README.md) · [Reorder Point (ROP) →](reorder_point.md)
