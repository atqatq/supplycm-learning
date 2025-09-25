---
title: "Anticipation Inventory | supplycm Algorithm Library"
description: "Plain-English explanation of anticipation_inventory from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, anticipation_inventory, supply chain, plain english, inventory"
---

# Anticipation Inventory

> **Call it:** `from supplycm.inventory import anticipation_inventory` · **Level:** Intermediate · **You need:** basic arithmetic only

Anticipation inventory is stock built AHEAD of known demand waves - holiday peaks, promotions, planned shutdowns. The function computes the pre-build needed when forecast demand exceeds production capacity. It is deliberate stocking, with a schedule attached.

**Think of it like this:** Squirrels with acorns - except the squirrels know exactly how long winter is.

## When to reach for it

- Building toward predictable seasonal peaks
- Planning production ahead of a planned maintenance shutdown

## Try it with supplycm

```python
from supplycm.inventory import anticipation_inventory

result = anticipation_inventory(demand_forecast=[100, 100, 400, 400, 100, 100], production_capacity=200)
print(result)
```

You should see something like:

```text
[100.0, 200.0, 0, 0, 0, 0]
```

Pre-build quantities per period - surplus production in calm months stacks up to cover the 400-unit months that capacity cannot serve.

## Check yourself

1. Anticipation vs safety stock - what's the difference?
2. What does holding anticipation stock cost vs alternatives?
3. When does anticipation stock backfire?

<details>
<summary>Show answers</summary>

1. Anticipation covers FORESEEN waves; safety stock covers random surprises. One is a plan, the other an insurance policy.

2. Holding cost vs overtime/outsource premiums - compute both; the answer flips by industry.

3. When the 'known' peak disappoints - now you hold seasonal stock with no season; hedge with flexible capacity where possible.

</details>

## Try this now

Compute the pre-build plan for demand [150, 150, 500, 500, 100, 100] with capacity 250 and state total carrying exposure.

---
[← Pipeline Inventory](pipeline_inventory.md) · [Back to Inventory library](README.md) · [Decoupling Inventory →](decoupling_inventory.md)
