---
title: "Expected On-Hand Inventory | supplycm Algorithm Library"
description: "Plain-English explanation of expected_on_hand from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, expected_on_hand, supply chain, plain english, inventory"
---

# Expected On-Hand Inventory

> **Call it:** `from supplycm.inventory import expected_on_hand` · **Level:** Advanced · **You need:** basic arithmetic only

Expected on-hand is the average PHYSICAL stock you hold under a given policy - safety stock plus roughly half the order quantity, minus expected shortages. It is the honest input for holding cost and for anyone asking 'why is the warehouse so full?'

**Think of it like this:** Your average bank balance across the month - not the payday spike, the number that actually earns (or costs) interest.

## When to reach for it

- Computing true holding cost of a proposed policy
- Explaining expected warehouse occupancy to operations

## Try it with supplycm

```python
from supplycm.inventory import expected_on_hand

result = expected_on_hand(safety_stock=30, demand_std=12, lead_time=4, order_quantity=600)
print(result)
```

You should see something like:

```text
330.0
```

Roughly 330 units on average - half the cycle stock sits atop the safety cushion, and shortages barely dent it.

## Check yourself

1. Why does average on-hand include half the order quantity?
2. On-hand vs inventory position - difference?
3. You cut order quantity in half. Average on-hand?

<details>
<summary>Show answers</summary>

1. Saw-tooth inventory: stock cycles between a peak and a trough, averaging in between.

2. On-hand is physical stock; position adds on-order and subtracts backorders - the number the reorder decision watches.

3. Drops by about a quarter of the old order size - but order frequency (and setup cost) rises.

</details>

## Try this now

Compute expected on-hand for order quantities 300 vs 900 at the same safety stock; price both at 25% holding.

---
[← Expected Backorder Units](expected_backorder.md) · [Back to Inventory library](README.md) · [Stockout Cost →](stockout_cost.md)
