---
title: "Shrinkage Factor | supplycm Algorithm Library"
description: "Plain-English explanation of shrinkage_factor from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, shrinkage_factor, supply chain, plain english, mrp & production planning"
---

# Shrinkage Factor

> **Call it:** `from supplycm.mrp import shrinkage_factor` · **Level:** Beginner · **You need:** basic arithmetic only

Shrinkage is the share that disappears: scrap on the line, damage, theft, yield loss. To END with 100 good units when 5% shrinks, you must START with about 105. This converts a net requirement into the gross requirement that respects the loss.

**Think of it like this:** Buying fruit for a fruit salad: peel and pits mean you buy more fruit than the bowl will hold.

## When to reach for it

- Grossing up MRP requirements for scrap and yield loss
- Auditing where 'missing' units vanish between plan and shelf

## Try it with supplycm

```python
from supplycm.mrp import shrinkage_factor

result = shrinkage_factor(gross_requirement=100, shrinkage_rate=0.05)
print(result)
```

You should see something like:

```text
105.2632
```

About 105.3 - start from there to finish at 100 good units after the 5% disappears.

## Check yourself

1. Why divide by (1 - rate) instead of just adding 5%?
2. Shrinkage 40% - alarm bells?
3. Different shrinkage per step in a 3-step process. Now what?

<details>
<summary>Show answers</summary>

1. Because the loss applies to the STARTING quantity - dividing compounds correctly; adding under-covers.

2. Yes - that is a process problem, not a planning parameter; investigate before planning around it.

3. Apply each step's factor in sequence - the compound loss is bigger than any single step suggests.

</details>

## Try this now

You need 500 good units; steps lose 3% then 2%. Compute the true starting quantity by hand, then per-step with the function.

---
[← Planning BOM (Option Percentages)](planning_bom.md) · [Back to MRP & Production Planning library](README.md) · [Safety Lead Time →](safety_lead_time.md)
