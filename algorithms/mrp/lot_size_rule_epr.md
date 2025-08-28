---
title: "Economic Part Period (EPP) Lot Sizing | supplycm Algorithm Library"
description: "Plain-English explanation of lot_size_rule_epr from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, lot_size_rule_epr, supply chain, plain english, mrp & production planning"
---

# Economic Part Period (EPP) Lot Sizing

> **Call it:** `from supplycm.mrp import lot_size_rule_epr` · **Level:** Advanced · **You need:** basic arithmetic only

EPP balances setup and holding automatically: compute how many 'part-periods' (units x periods held) of holding one setup can justify, then extend an order only while the accumulated holding stays under that budget. It is a smarter POQ that adapts to demand shape.

**Think of it like this:** Deciding how many errands to bundle into one trip: each extra stop adds 'waiting cost', and you keep adding stops until waiting would cost a new trip anyway.

## When to reach for it

- Lumpy demand where fixed POQ periods misfit
- Teaching the setup-vs-holding trade-off with actual arithmetic

## Try it with supplycm

```python
from supplycm.mrp import lot_size_rule_epr

result = lot_size_rule_epr(net_requirements=[10, 20, 30, 40], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[60, 0.0, 0.0, 40]
```

Bundled order quantities come back - watch the rule extend a lot while holding stays cheaper than another setup, then stop.

## Check yourself

1. What is a 'part-period'?
2. How is the EPP threshold computed?
3. Demand spikes once then vanishes. What does EPP do?

<details>
<summary>Show answers</summary>

1. One unit held for one period - the common currency that lets setup cost and holding cost be compared.

2. Roughly setup_cost / holding_cost - the number of part-periods a setup can 'afford'.

3. It covers the spike in one lot and stops extending - the holding budget naturally refuses to carry dead demand.

</details>

## Try this now

Compute EPP = setup/holding for setup 90, holding 1; then verify the function never bundles beyond it.

---
[← Period Order Quantity (POQ)](lot_size_rule_poq.md) · [Back to MRP & Production Planning library](README.md) · [Minimum Order Quantity (MOQ) →](minimum_order_quantity.md)
