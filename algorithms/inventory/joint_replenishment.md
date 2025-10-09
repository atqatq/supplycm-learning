---
title: "Joint Replenishment | supplycm Algorithm Library"
description: "Plain-English explanation of joint_replenishment from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, joint_replenishment, supply chain, plain english, inventory"
---

# Joint Replenishment

> **Call it:** `from supplycm.inventory import joint_replenishment` · **Level:** Advanced · **You need:** basic arithmetic only

Ordering several items from one supplier on one truck shares the major setup cost - but each item still has its own minor costs and holding. This computes a common review cycle and per-item order quantities that split the shared cost fairly and economically.

**Think of it like this:** A group grocery order: one delivery fee (shared) plus everyone's personal items - the group cycle sets how often the van comes.

## When to reach for it

- Multi-item orders from a single supplier or lane
- Cutting total ordering cost by coordinating schedules

## Try it with supplycm

```python
from supplycm.inventory import joint_replenishment

result = joint_replenishment(demands=[100, 200, 300], major_setup=100, minor_setup=[10, 20, 30], holding_costs=[1, 2, 3])
print(result)
```

You should see something like:

```text
[0.4781, [47.8091, 95.6183, 143.4274]]
```

A common cycle time plus order quantities per item - slower cycles than solo ordering, but the shared truck makes the total cheaper.

## Check yourself

1. What's the difference between major and minor setup costs?
2. Why not just order each item on its own EOQ schedule?
3. When does joint replenishment backfire?

<details>
<summary>Show answers</summary>

1. Major: cost of the order/shipment itself (paid once per joint order); minor: per-item handling added for each item included.

2. You'd pay the major cost three times - coordination buys discounts on the shared part.

3. Wildly different demand rates - forcing one cycle means slow items ride along with expensive extra holding.

</details>

## Try this now

Recompute with major_setup=500 and explain why the common cycle lengthens.

---
[← Base-Stock (Order-Up-To) Policy](base_stock_policy.md) · [Back to Inventory library](README.md) · [Multi-Echelon Inventory →](multi_echelon_inventory.md)
