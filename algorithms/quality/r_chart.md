---
title: "R Control Chart | supplycm Algorithm Library"
description: "Plain-English explanation of r_chart from the supplycm Quality module, with a runnable Python example and self-check questions."
keywords: "supplycm, quality, r_chart, supply chain, plain english, quality"
---

# R Control Chart

> **Call it:** `from supplycm.quality import r_chart` · **Level:** Intermediate · **You need:** basic arithmetic only

The R chart tracks the RANGE (biggest minus smallest) within each sample - it watches the process's consistency, while the X-bar chart watches its average. You always read them as a pair: average first (where is it?), then range (how steady is it?).

**Think of it like this:** Blood-pressure monitor's two numbers: one for the level, one for the pulse of variability.

## When to reach for it

- Pairing with X-bar to see whether averages or spread misbehave
- Catching inconsistent operators, materials, or machines

## Try it with supplycm

```python
from supplycm.quality import r_chart

result = r_chart([[10.0, 10.4, 9.8], [10.1, 10.0, 10.2], [9.5, 10.6, 10.4]])
print(result)
```

You should see something like:

```text
[[0.6, 0.2, 1.1], 1.6302, 0.0]
```

The third sample's range balloons past the limit - within that sample, values scattered wildly: a consistency problem, not an average problem.

## Check yourself

1. What exactly does each point on the R chart show?
2. X-bar in control, R chart out of control. What does that mean?
3. Why must you check R before X-bar?

<details>
<summary>Show answers</summary>

1. The range (max - min) of one sample - how scattered that sample was.

2. The average is stable but the spread is not - parts are inconsistent even though the center holds.

3. The X-bar limits are computed FROM the ranges - if spread is unstable, the average chart's limits are built on sand.

</details>

## Try this now

Build 5 samples where the spread widens over time but the average stays flat; show both charts disagree with 'all is well'.

---
[← X-Bar Control Chart](x_bar_chart.md) · [Back to Quality library](README.md) · [P Control Chart →](p_chart.md)

*New to this topic? Start with the core lesson first: [07_quality.md](../../modules/07_quality.md).*
