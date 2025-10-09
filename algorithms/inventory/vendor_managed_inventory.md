---
title: "Vendor Managed Inventory (VMI) | supplycm Algorithm Library"
description: "Plain-English explanation of vendor_managed_inventory from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, vendor_managed_inventory, supply chain, plain english, inventory"
---

# Vendor Managed Inventory (VMI)

> **Call it:** `from supplycm.inventory import vendor_managed_inventory` · **Level:** Intermediate · **You need:** basic arithmetic only

Under VMI the SUPPLIER watches your stock and decides replenishment - typically holding some inventory on your site (consignment). This computes the joint optimal order quantity when vendor and buyer holding costs are shared: the total system beats two silos optimizing separately.

**Think of it like this:** Your fridge stocked by the grocery store: they see the shelves, they schedule the van - nobody double-buys, nobody panic-buys.

## When to reach for it

- Stable, high-volume supplier relationships
- Situations where stockouts and overstock bounce between two uncoordinated planners

## Try it with supplycm

```python
from supplycm.inventory import vendor_managed_inventory

result = vendor_managed_inventory(demand=1000, setup_cost=100, holding_cost_vendor=3, holding_cost_buyer=2)
print(result)
```

You should see something like:

```text
200.0
```

A joint EOQ around 200 - larger than either party would choose alone, because the combined holding pool changes the economics.

## Check yourself

1. Who decides order timing under VMI?
2. Why does joint optimization beat two separate EOQs?
3. What makes VMI relationships fail?

<details>
<summary>Show answers</summary>

1. The supplier, within agreed service targets - using shared consumption data instead of purchase orders.

2. Silos double-count protection - sharing data (and cost visibility) removes duplicated buffers.

3. Opaque data, mistrust, and unshared benefits - the math only works when both sides see the same truth.

</details>

## Try this now

Compare VMI joint EOQ vs a buyer-only EOQ (holding 5) - quantify the order-size change and who benefits.

---
[← Multi-Echelon Inventory](multi_echelon_inventory.md) · [Back to Inventory library](README.md) · [Ordering Cost Allocation →](ordering_cost_allocation.md)
