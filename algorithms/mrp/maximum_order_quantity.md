---
title: "Maximum Order Quantity (MaxOQ) | supplycm Algorithm Library"
description: "Plain-English explanation of maximum_order_quantity from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, maximum_order_quantity, supply chain, plain english, mrp & production planning"
---

# Maximum Order Quantity (MaxOQ)

> **Call it:** `from supplycm.mrp import maximum_order_quantity` · **Level:** Intermediate · **You need:** basic arithmetic only

The opposite guardrail: caps how big a single order may be - capacity limits, truck sizes, budget rules, or cash constraints. Needs above the cap split across periods. It forces the plan to respect real-world ceilings instead of dreaming.

**Think of it like this:** A credit card limit while shopping: you may want it all today, but the card decides the pace.

## When to reach for it

- Production lines or suppliers with hard capacity caps
- Cash-flow constrained purchasing

## Try it with supplycm

```python
from supplycm.mrp import maximum_order_quantity

result = maximum_order_quantity(net_requirements=[80, 120, 40], max_qty=100)
print(result)
```

You should see something like:

```text
[80.0, 60.0, 60.0, 40.0]
```

120 is trimmed to 100 - the leftover 20 must be covered by the next order, which the plan shifts accordingly.

## Check yourself

1. What happens to demand the cap cannot cover this period?
2. Why set caps at all if MRP says order 150?
3. Cap forces a split - what should you check next?

<details>
<summary>Show answers</summary>

1. It moves to a later order - which may violate a due date unless you pre-build or expedite.

2. Because the machine makes 100 max per run - MRP plans need, caps keep plans physically possible.

3. Capacity in the following period for the leftover, and holding cost of any earlier pre-build.

</details>

## Try this now

Cap [200, 200, 200] at 150 per order; plan releases by hand and flag any period where the cap breaks feasibility.

---
[← Minimum Order Quantity (MOQ)](minimum_order_quantity.md) · [Back to MRP & Production Planning library](README.md) · [Order Multiples →](order_multiples.md)
