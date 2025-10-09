---
title: "Spare Parts: FSN Classification | supplycm Algorithm Library"
description: "Plain-English explanation of spare_parts_fsn from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, spare_parts_fsn, supply chain, plain english, inventory"
---

# Spare Parts: FSN Classification

> **Call it:** `from supplycm.inventory import spare_parts_fsn` · **Level:** Intermediate · **You need:** basic arithmetic only

FSN classifies spares by MOVEMENT: Fast movers (issued constantly), Slow movers (occasional), Non-movers (dust). Storage follows: fast parts live at the technician's elbow, non-movers go to cheap remote shelves. Movement, not value, decides geography.

**Think of it like this:** A kitchen: salt on the counter, occasional spices in the cupboard, the turkey platter in the attic.

## When to reach for it

- Laying out spare-parts storerooms
- Deciding which parts deserve forward picking locations

## Try it with supplycm

```python
from supplycm.inventory import spare_parts_fsn

result = spare_parts_fsn(usage_data=[('filter', 800.0, 1000.0), ('pump', 350.0, 1000.0), ('legacy-valve', 5.0, 1000.0)])
print(result)
```

You should see something like:

```text
[['filter', 'F'], ['pump', 'S'], ['legacy-valve', 'N']]
```

Classes come back: the filter is F, the pump S, the legacy valve N - three different homes and three different review rhythms.

## Check yourself

1. Why manage non-movers at all if they never move?
2. Where should F items physically live?
3. How do FSN and VED combine?

<details>
<summary>Show answers</summary>

1. Because 'rarely' is not 'never' - a dead line waiting on a dusty valve costs more than the shelf space ever did.

2. As close to the point of use as possible - every meter of travel multiplies by thousands of picks.

3. They form a grid: a Vital-but-Non-moving part gets secure, documented storage; Fast-but-noncritical gets bulk cheap bins.

</details>

## Try this now

FSN-classify 8 spares from invented usage counts and assign each a storage zone and count frequency.

---
[← Ordering Cost Allocation](ordering_cost_allocation.md) · [Back to Inventory library](README.md) · [Spare Parts: VED Classification →](spare_parts_ved.md)
