---
title: "Economic Order Quantity (EOQ) | supplycm Algorithm Library"
description: "Plain-English explanation of economic_order_quantity from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, economic_order_quantity, supply chain, plain english, inventory"
---

# Economic Order Quantity (EOQ)

> **Call it:** `from supplycm.inventory import economic_order_quantity` · **Level:** Beginner · **You need:** basic arithmetic only

EOQ answers the oldest question in purchasing: HOW MUCH should we order? Order often (small batches) and setup costs pile up; order rarely (big batches) and inventory costs pile up. EOQ is the batch size where the two costs balance - one number you can defend to anyone.

**Think of it like this:** Grocery shopping: going daily wastes trips, buying a year of milk wastes milk. The best shopping quantity sits in between.

## When to reach for it

- Setting standard order sizes for steady, predictable products
- Quick sanity check on whether current order sizes are way off

## Try it with supplycm

```python
from supplycm.inventory import economic_order_quantity

result = economic_order_quantity(demand=1200, ordering_cost=50, holding_cost=2)
print(result)
```

You should see something like:

```text
244.949
```

About 245 units per order - order that much each time demand allows, roughly 5 times a year.

> **Watch out:** Even when assumptions bend, EOQ stays useful as a ballpark - just don't treat it as gospel.

## Check yourself

1. What two costs does EOQ balance?
2. Demand quadruples. Does EOQ quadruple?
3. Name two assumptions EOQ quietly makes.

<details>
<summary>Show answers</summary>

1. Ordering/setup cost (more orders = more cost) and holding cost (more stock = more cost).

2. No - it doubles. EOQ grows with the SQUARE ROOT of demand, which surprises most people.

3. Demand is steady and costs are fixed per order/unit - real world violations call for dynamic lot sizing.

</details>

## Try this now

Compute EOQ for demand 900, ordering 40, holding 1.8; then estimate orders per year and check the function agrees.

---
[Back to Inventory library](README.md) · [Inventory Carrying Rate →](inventory_carrying_rate.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
