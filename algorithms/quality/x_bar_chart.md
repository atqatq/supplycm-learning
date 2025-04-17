---
title: "X-Bar Control Chart | supplycm Algorithm Library"
description: "Plain-English explanation of x_bar_chart from the supplycm Quality module, with a runnable Python example and self-check questions."
keywords: "supplycm, quality, x_bar_chart, supply chain, plain english, quality"
---

# X-Bar Control Chart

> **Call it:** `from supplycm.quality import x_bar_chart` · **Level:** Intermediate · **You need:** basic arithmetic only

The X-bar chart tracks the AVERAGE of small samples over time and draws control limits around it. Points inside the limits mean the process average is stable; a point outside (or a run drifting) signals a special cause worth hunting. It watches the center of the process.

**Think of it like this:** A heart-rate monitor for your process average - beeping when the average does something it normally never does.

## When to reach for it

- Monitoring daily batch averages (fill weight, cycle time)
- Catching process drift before it produces out-of-spec product

## Try it with supplycm

```python
from supplycm.quality import x_bar_chart

result = x_bar_chart([[10.1, 10.0, 9.9], [10.2, 10.1, 10.0], [10.8, 10.9, 10.7]])
print(result)
```

You should see something like:

```text
[[10.0, 10.1, 10.8], 10.5046, 10.0954]
```

The third sample's average jumps outside the control limits - something special happened around then; investigate that shift, not the whole process.

## Check yourself

1. Control limits vs spec limits - different things?
2. What is a 'special cause'?
3. Sample averages stay in limits but drift upward for 7 points. Problem?

<details>
<summary>Show answers</summary>

1. Yes! Control limits come from the process voice (its natural variation); specs come from the customer. A process can be 'in control' and still out of spec.

2. Something unusual - a bad material lot, a new operator - that pushes the process beyond its normal wobble.

3. Yes - runs and trends count as out-of-control signals even inside the limits.

</details>

## Try this now

Chart 6 sample averages you invent, including one late drift; identify the point where you'd intervene.

---
[← Process Capability (Cpk)](process_capability_cpk.md) · [Back to Quality library](README.md) · [R Control Chart →](r_chart.md)

*New to this topic? Start with the core lesson first: [07_quality.md](../../modules/07_quality.md).*
