---
title: "Modular BOM | supplycm Algorithm Library"
description: "Plain-English explanation of modular_bom from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, modular_bom, supply chain, plain english, mrp & production planning"
---

# Modular BOM

> **Call it:** `from supplycm.mrp import modular_bom` · **Level:** Intermediate · **You need:** basic arithmetic only

For product families built from modules (laptops: screen + CPU + case), a modular BOM plans MODULES instead of every finished-goods variant. Feed family demand and each module's ratio; get module requirements. Planning 5 modules beats planning 200 variant SKUs.

**Think of it like this:** A sandwich shop plans bread, fillings, and sauces by average usage - not by forecasting every possible sandwich combination.

## When to reach for it

- Configure-to-order products with many variants
- Reducing forecast error by forecasting common modules

## Try it with supplycm

```python
from supplycm.mrp import modular_bom

result = modular_bom(product_family_demand={'laptop': 1000.0}, module_ratios={'laptop': {'screen14': 0.6, 'screen15': 0.4, 'battery': 1.0}})
print(result)
```

You should see something like:

```text
{'screen14': 600.0, 'screen15': 400.0, 'battery': 1000.0}
```

Module needs come back: 600 + 400 screens and 1,000 batteries - two screen modules to plan instead of every laptop variant.

## Check yourself

1. Why is module forecasting more accurate than variant forecasting?
2. A new variant mixes modules in new ratios. What changes?
3. Where do module ratios come from?

<details>
<summary>Show answers</summary>

1. Variants split demand into noisy streams; modules aggregate it - noise cancels and percentages are stabler.

2. Only the ratio table - the module plan adapts without new forecasting models.

3. Recent actual sales mix, updated regularly - stale ratios quietly mis-plan.

</details>

## Try this now

A bike family (3 frame sizes, 2 brake types) has demand 2,000. Write ratios, compute module needs, and count the SKUs you avoided forecasting.

---
[← Where-Used Query](where_used_query.md) · [Back to MRP & Production Planning library](README.md) · [Planning BOM (Option Percentages) →](planning_bom.md)
