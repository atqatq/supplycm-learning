---
title: "Multi-Echelon Inventory | supplycm Algorithm Library"
description: "Plain-English explanation of multi_echelon_inventory from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, multi_echelon_inventory, supply chain, plain english, inventory"
---

# Multi-Echelon Inventory

> **Call it:** `from supplycm.inventory import multi_echelon_inventory` · **Level:** Advanced · **You need:** basic arithmetic only

A supply chain is a relay: factory -> DC -> stores. Stocking each stage as if alone wastes money; echelon stock math allocates safety stock ACROSS stages, favoring cheaper, upstream positions while keeping service at the customer end. This simplified serial version shows the trade.

**Think of it like this:** A road trip: fuel in the tank, a can in the trunk, and a station ahead - the total reserve matters, and the cheapest container should carry more.

## When to reach for it

- Setting safety stock across DC-to-store networks
- Understanding why upstream stock is (usually) cheaper than downstream stock

## Try it with supplycm

```python
from supplycm.inventory import multi_echelon_inventory

result = multi_echelon_inventory(demand_rate=50, demand_std=10, echelons=[(2, 1), (5, 1)], holding_costs=[1, 3])
print(result)
```

You should see something like:

```text
[[27.7186, 127.7186], [51.8567, 401.8567]]
```

Safety stock per echelon - notice how the math leans toward the cheaper upstream echelon while still protecting the customer-facing stage.

## Check yourself

1. What is an 'echelon'?
2. Why is upstream stock often cheaper to hold?
3. What's the risk of starving the downstream echelon?

<details>
<summary>Show answers</summary>

1. One stage of the chain (factory, regional DC, local store) - each adds lead time and holds its own stock.

2. Storage and capital costs run lower away from expensive retail space - and pooling is easier upstream.

3. Customer service collapses - the optimization's whole job is balancing cheap-upstream against close-to-customer.

</details>

## Try this now

Double the downstream holding cost and observe how the allocation shifts upstream - narrate the economics.

---
[← Joint Replenishment](joint_replenishment.md) · [Back to Inventory library](README.md) · [Vendor Managed Inventory (VMI) →](vendor_managed_inventory.md)
