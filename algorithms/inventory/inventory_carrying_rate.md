---
title: "Inventory Carrying Rate | supplycm Algorithm Library"
description: "Plain-English explanation of inventory_carrying_rate from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, inventory_carrying_rate, supply chain, plain english, inventory"
---

# Inventory Carrying Rate

> **Call it:** `from supplycm.inventory import inventory_carrying_rate` · **Level:** Beginner · **You need:** basic arithmetic only

Before you can cost inventory, you need the carrying rate: what percentage of an item's value it costs to hold it for a year. It bundles capital cost, storage, insurance, and the risk of damage or obsolescence. Most businesses land between 15% and 30%.

**Think of it like this:** The true yearly cost of owning a car as a percentage of its price: parking, insurance, depreciation - it all adds up to a rate.

## When to reach for it

- Establishing the holding_cost input for EOQ and safety stock math
- Challenging managers who claim 'holding inventory is free'

## Try it with supplycm

```python
from supplycm.inventory import inventory_carrying_rate

result = inventory_carrying_rate(capital_cost=8000, storage_cost=3000, risk_cost=2000, inventory_value=50000)
print(result)
```

You should see something like:

```text
0.26
```

26% - every dollar of inventory costs 26 cents per year to keep. That is the number that makes overstock real.

## Check yourself

1. Name the components of the carrying rate.
2. Why is 25% a common rule of thumb?
3. Interest rates double. What happens to your carrying rate?

<details>
<summary>Show answers</summary>

1. Capital (money tied up), storage (space, utilities), and risk (shrinkage, damage, obsolescence).

2. Capital ~10%, storage ~5-10%, risk ~5-10% - they stack up fast once you count honestly.

3. The capital component rises, pushing the whole rate up - and optimal order sizes down.

</details>

## Try this now

Build the carrying rate for a business you know with honest component guesses; compare with the 20-30% range.

---
[← Economic Order Quantity (EOQ)](economic_order_quantity.md) · [Back to Inventory library](README.md) · [Holding Cost Calculation →](holding_cost_calculation.md)
