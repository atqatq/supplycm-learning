---
title: "Bootstrap Confidence Interval | supplycm Algorithm Library"
description: "Plain-English explanation of bootstrap_confidence_interval from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, bootstrap_confidence_interval, supply chain, plain english, statistics & accuracy"
---

# Bootstrap Confidence Interval

> **Call it:** `from supplycm.statistics import bootstrap_confidence_interval` · **Level:** Intermediate · **You need:** basic arithmetic only

The bootstrap builds confidence intervals by repeatedly resampling your own data (with a fixed seed so results repeat). It asks 'what would the answer look like if I had collected slightly different samples?' thousands of times. No formulas needed - just resampling and counting, which fits our basic-arithmetic-only rule.

**Think of it like this:** Like replaying a season thousands of times with small twists to see the realistic range of final standings.

## When to reach for it

- Getting a reliable interval when the data is skewed or weird
- Any time a textbook formula feels too fragile for your messy data

## Try it with supplycm

```python
from supplycm.statistics import bootstrap_confidence_interval

result = bootstrap_confidence_interval([48, 52, 45, 55, 50, 47, 53, 49, 200], n_bootstrap=2000)
print(result)
```

You should see something like:

```text
[48.3333, 100.2222]
```

The interval stretches at the top because of that one 200 - the bootstrap honestly reflects how suspicious the extreme value makes the average.

## Check yourself

1. Why does the bootstrap need a seed?
2. What is 'resampling with replacement'?
3. When would you prefer bootstrap over a formula-based interval?

<details>
<summary>Show answers</summary>

1. It uses random resampling; the seed makes results reproducible run after run.

2. Drawing new samples from your data where each drawn value goes back into the pool and can be drawn again.

3. When data is skewed, has outliers, or the sample is small and the standard formula is shaky.

</details>

## Try this now

Bootstrap an interval for your own 20 values twice with the same seed and confirm you get the same answer both times.

---
[← Confidence Interval for a Mean](confidence_interval_mean.md) · [Back to Statistics & Accuracy library](README.md) · [Moving Average Smoothing →](moving_average_smooth.md)
