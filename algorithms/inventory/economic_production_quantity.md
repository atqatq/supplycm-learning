---
title: "Economic Production Quantity (EPQ) | supplycm Algorithm Library"
description: "Plain-English explanation of economic_production_quantity from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, economic_production_quantity, supply chain, plain english, inventory"
---

# Economic Production Quantity (EPQ)

> **Call it:** `from supplycm.inventory import economic_production_quantity` · **Level:** Intermediate · **You need:** basic arithmetic only

EPQ is EOQ's cousin for making items yourself: the machine produces AND demand drains stock at the same time, so peak inventory is lower than the batch size. EPQ finds the run size that balances setup cost against this gentler inventory build-up.

**Think of it like this:** Filling a bathtub while the drain is open: water rises slower than the tap's flow - the tub peaks at less than the full batch.

## When to reach for it

- In-house production runs on machines with setup times
- Comparing make-quantity decisions with purchase-quantity decisions

## Try it with supplycm

```python
from supplycm.inventory import economic_production_quantity

result = economic_production_quantity(demand=1200, production=2400, setup_cost=300, holding_cost=2)
print(result)
```

You should see something like:

```text
848.5281
```

A larger run than plain EOQ would suggest - because production rate above demand keeps inventory from ever reaching the full batch size.

## Check yourself

1. Why is EPQ larger than EOQ for the same item?
2. Production rate equals demand rate. What happens?
3. What replaces 'ordering cost' in EPQ?

<details>
<summary>Show answers</summary>

1. Because simultaneous demand drains the stock during production - peak inventory is a fraction of the run, so bigger runs cost less than you'd think.

2. The formula explodes - you can never build ahead, every unit ships as made (the drain matches the tap).

3. Setup cost - the time and money to switch the machine to this product.

</details>

## Try this now

Compute EPQ for demand 1000, production 4000, setup 200, holding 1.5, and compare it with plain EOQ on the same numbers.

---
[← Holding Cost Calculation](holding_cost_calculation.md) · [Back to Inventory library](README.md) · [EOQ with Backorders →](eoq_with_backorders.md)
