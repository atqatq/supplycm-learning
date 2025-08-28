---
title: "Fixed Order Quantity (FOQ) | supplycm Algorithm Library"
description: "Plain-English explanation of lot_size_rule_foq from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, lot_size_rule_foq, supply chain, plain english, mrp & production planning"
---

# Fixed Order Quantity (FOQ)

> **Call it:** `from supplycm.mrp import lot_size_rule_foq` · **Level:** Beginner · **You need:** basic arithmetic only

FOQ always orders the same amount - 100 is 100, every time, possibly rounding up past the need. Simple to run, easy for suppliers, friendly to machinery with fixed batch sizes. The price is leftover inventory in small-demand periods.

**Think of it like this:** Buying eggs by the dozen whatever the recipe needs - convenient, occasionally wasteful.

## When to reach for it

- Processes with natural batch sizes (oven, mold, truck)
- Simplicity-first operations without planning software

## Try it with supplycm

```python
from supplycm.mrp import lot_size_rule_foq

result = lot_size_rule_foq(net_requirements=[10, 40, 0, 90], fixed_q=50)
print(result)
```

You should see something like:

```text
[50, 50, 0, 100]
```

Orders of 50, 50, 0, 100 - needs get rounded up to fixed chunks, so some periods carry leftovers forward.

## Check yourself

1. What happens when the requirement is 10 and FOQ is 50?
2. Why do suppliers love FOQ?
3. When does FOQ become expensive?

<details>
<summary>Show answers</summary>

1. You order 50 - the extra 40 waits as inventory for future periods.

2. Predictable volumes mean stable production runs and easier logistics on their side.

3. Erratic small demands - rounding waste piles up; consider L4L or period quantities instead.

</details>

## Try this now

For needs [5, 70, 10, 45] with FOQ 40, track on-hand inventory period by period by hand.

---
[← Lot-for-Lot (L4L)](lot_size_rule_l4l.md) · [Back to MRP & Production Planning library](README.md) · [Period Order Quantity (POQ) →](lot_size_rule_poq.md)
