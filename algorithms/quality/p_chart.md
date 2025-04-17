---
title: "P Control Chart | supplycm Algorithm Library"
description: "Plain-English explanation of p_chart from the supplycm Quality module, with a runnable Python example and self-check questions."
keywords: "supplycm, quality, p_chart, supply chain, plain english, quality"
---

# P Control Chart

> **Call it:** `from supplycm.quality import p_chart` · **Level:** Intermediate · **You need:** basic arithmetic only

The p chart tracks the PROPORTION of defective items in samples - perfect for pass/fail data like '3 of 100 deliveries late'. Control limits adapt to each sample size, so small samples get wider limits. It is the quality tool for counts of bad units.

**Think of it like this:** Tracking your free-throw percentage game by game, with honest uncertainty bands when you took fewer shots.

## When to reach for it

- Monitoring defect or late-delivery percentages over time
- Processes judged by pass/fail rather than measurements

## Try it with supplycm

```python
from supplycm.quality import p_chart

result = p_chart(defectives=[3, 5, 2, 9], sample_sizes=[100, 100, 100, 100])
print(result)
```

You should see something like:

```text
[[0.03, 0.05, 0.02, 0.09], 0.0475, 0.1113, 0]
```

The fourth sample's defect share escapes the upper limit - that day was special-cause bad; find out what happened.

## Check yourself

1. When do you choose a p chart over X-bar/R?
2. Why do limits change with sample size?
3. A supplier's late-delivery % p chart trends up for 6 weeks. Action?

<details>
<summary>Show answers</summary>

1. When the data is pass/fail counts (attribute data), not measurements.

2. Small samples carry more uncertainty, so the limits honestly widen to avoid false alarms.

3. Treat it as a real deterioration signal - start the escalation ladder before it escapes the limits.

</details>

## Try this now

Track 8 weeks of 'late deliveries out of 50' with a mild upward creep; would you have caught it before a point escaped?

---
[← R Control Chart](r_chart.md) · [Back to Quality library](README.md)

*New to this topic? Start with the core lesson first: [07_quality.md](../../modules/07_quality.md).*
