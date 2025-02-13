---
title: "Confidence Interval for a Mean | supplycm Algorithm Library"
description: "Plain-English explanation of confidence_interval_mean from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, confidence_interval_mean, supply chain, plain english, statistics & accuracy"
---

# Confidence Interval for a Mean

> **Call it:** `from supplycm.statistics import confidence_interval_mean` · **Level:** Intermediate · **You need:** basic arithmetic only

A confidence interval wraps a range around your average: 'true demand is likely between X and Y'. It combines the average, the spread, and the sample size. Narrow intervals mean you know the level well; wide ones mean you need more data or more buffer.

**Think of it like this:** Like a fishing net around your estimate: a wider net is more likely to hold the true value, but tells you less precisely where it is.

## When to reach for it

- Stating demand estimates honestly in a planning meeting
- Deciding whether you have enough history to plan confidently

## Try it with supplycm

```python
from supplycm.statistics import confidence_interval_mean

result = confidence_interval_mean([48, 52, 45, 55, 50, 47, 53, 49])
print(result)
```

You should see something like:

```text
[47.5786, 52.1714]
```

The average sits inside a fairly tight band - with 8 weeks like these, weekly demand is pinned down to within a few units.

## Check yourself

1. What three things control the width of the interval?
2. Does a 95% interval mean there is a 95% chance the mean is inside this exact interval?
3. You want a narrower interval. Name two honest ways.

<details>
<summary>Show answers</summary>

1. How spread out the data is, how many points you have, and the confidence level you demand.

2. Loosely: if you repeated the whole process many times, about 95% of such intervals would capture the true mean.

3. Collect more data, or accept a lower confidence level (e.g., 90% instead of 99%).

</details>

## Try this now

Compute intervals for 8 samples vs 32 samples of similar data and show how the width shrinks.

---
[← Adjusted R-Squared](adjusted_r_squared.md) · [Back to Statistics & Accuracy library](README.md) · [Bootstrap Confidence Interval →](bootstrap_confidence_interval.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
