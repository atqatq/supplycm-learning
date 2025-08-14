---
title: "Planning BOM (Option Percentages) | supplycm Algorithm Library"
description: "Plain-English explanation of planning_bom from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, planning_bom, supply chain, plain english, mrp & production planning"
---

# Planning BOM (Option Percentages)

> **Call it:** `from supplycm.mrp import planning_bom` · **Level:** Intermediate · **You need:** basic arithmetic only

A planning BOM replaces exact variant counts with percentages: 'of 1,000 units, 30% will be red, 50% blue, 20% green'. One call multiplies the family forecast into option requirements. It is the simplest tool for planning when exact mixes are unknown.

**Think of it like this:** The sandwich shop's 'we sell 60% chicken, 40% veggie' rule - one forecast, two prep trays.

## When to reach for it

- Planning options/colors/sizes without full variant SKUs
- Rough-sizing long-lead option components

## Try it with supplycm

```python
from supplycm.mrp import planning_bom

result = planning_bom(forecast=1000, option_percentages={'red': 0.3, 'blue': 0.5, 'green': 0.2})
print(result)
```

You should see something like:

```text
{'red': 300.0, 'blue': 500.0, 'green': 200.0}
```

300 red, 500 blue, 200 green - percentages do the disaggregation when history cannot give you exact variant forecasts.

## Check yourself

1. Where do the percentages come from?
2. Percentages sum to 0.95. Problem?
3. One color trends from 20% to 35% over months. Action?

<details>
<summary>Show answers</summary>

1. Historical sales mix - adjusted for known shifts like a new color launch.

2. Yes - 5% of demand is unplanned; percentages should cover 100% or you knowingly hold a buffer.

3. Update the planning percentages gradually - chasing one month's mix overcorrects.

</details>

## Try this now

Plan options for 5,000 t-shirts across 3 sizes with your own percentages; verify they sum to 1.0 first.

---
[← Modular BOM](modular_bom.md) · [Back to MRP & Production Planning library](README.md) · [Shrinkage Factor →](shrinkage_factor.md)
