---
title: "Cycle Counting Plan | supplycm Algorithm Library"
description: "Plain-English explanation of cycle_counting from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, cycle_counting, supply chain, plain english, mrp & production planning"
---

# Cycle Counting Plan

> **Call it:** `from supplycm.mrp import cycle_counting` · **Level:** Intermediate · **You need:** basic arithmetic only

Instead of one dreaded annual wall-to-wall count, cycle counting counts a few items every day all year - A items often, C items rarely. This schedules items into count buckets by class and frequency, output as a month-by-month counting plan.

**Think of it like this:** Brushing teeth daily vs one brutal dental deep-clean a year - small steady effort beats the annual horror.

## When to reach for it

- Replacing annual physical inventories
- Keeping ERP inventory accuracy high enough for MRP to be trusted

## Try it with supplycm

```python
from supplycm.mrp import cycle_counting

result = cycle_counting(abc_classification=[('bolt', 'C'), ('motor', 'A'), ('cable', 'B'), ('pump', 'A')], counts_per_year={'A': 12, 'B': 4, 'C': 1})
print(result)
```

You should see something like:

```text
{0: ['bolt', 'motor', 'cable', 'pump'], 1: ['motor', 'pump'], 2: ['motor', 'pump'], 3: ['motor', 'cable', 'pump'], 4: ['motor', 'pump'], 5: ['motor', 'pump'], 6: ['motor', 'cable', 'pump'], 7: ['motor', 'pump'], 8: ['motor', 'pump'], 9: ['motor', 'cable', 'pump'], 10: ['motor', 'pump'], 11: ['motor', 'pump']}
```

A month -> items plan: motors and pumps appear monthly, bolts once a year - effort flows to where accuracy matters most.

## Check yourself

1. Why count A items 12 times a year and C items once?
2. What accuracy level should cycle counting target?
3. A count is off by 3%. Fix the number and move on?

<details>
<summary>Show answers</summary>

1. A errors cost the most and move fastest - accuracy effort should follow value at risk.

2. Commonly 95-99% by class (A highest) - below that, MRP orders start protecting against your own data.

3. No - investigate the root cause (process, location, transaction) or the error returns next count.

</details>

## Try this now

Build a 12-month plan for 10 items across A/B/C and verify every item's annual frequency matches its class.

---
[← Phantom BOM Handling](phantom_bom_handling.md) · [Back to MRP & Production Planning library](README.md) · [Rough-Cut Capacity Planning (RCCP) →](rough_cut_capacity_planning.md)
