---
title: "Bullwhip Effect Ratio | supplycm Algorithm Library"
description: "Plain-English explanation of bullwhip_effect from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, bullwhip_effect, supply chain, plain english, inventory"
---

# Bullwhip Effect Ratio

> **Call it:** `from supplycm.inventory import bullwhip_effect` · **Level:** Intermediate · **You need:** basic arithmetic only

Small wiggles in customer demand become giant waves in factory orders as each tier overreacts, batches, and hedges. This ratio compares order variability upstream with customer demand variability downstream - above 1.0 means the whip is cracking.

**Think of it like this:** A garden hose whip: a small wrist flick at your end becomes a violent snap at the nozzle - each joint amplifies.

## When to reach for it

- Diagnosing supply chain instability beyond your own four walls
- Quantifying the value of sharing POS data upstream

## Try it with supplycm

```python
from supplycm.inventory import bullwhip_effect

result = bullwhip_effect(customer_demand=[100, 102, 98, 101, 99, 100], order_pattern=[80, 130, 70, 140, 60, 120])
print(result)
```

You should see something like:

```text
580.0
```

A ratio well above 1 - customer demand barely breathes while orders rollercoaster; every tier upstream will feel earthquakes.

## Check yourself

1. What are the classic causes of bullwhip?
2. How does sharing POS data help?
3. Who suffers most from bullwhip?

<details>
<summary>Show answers</summary>

1. Demand-signal processing (forecasting on orders), order batching, price promotions, and shortage gaming.

2. It lets upstream see TRUE demand instead of amplified orders - cutting the biggest amplifier.

3. The farthest upstream tiers - suppliers see the wildest swings despite the calmest customer demand.

</details>

## Try this now

Generate two tiers of orders where each tier rounds demand to batches of 25; compute the ratio and explain the crack.

---
[← Risk Pooling Effect](risk_pooling.md) · [Back to Inventory library](README.md) · [Pipeline Inventory →](pipeline_inventory.md)
