---
title: "Descriptive Stats | supplycm Algorithm Library"
description: "Plain-English explanation of descriptive_stats from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, descriptive_stats, supply chain, plain english, statistics & accuracy"
---

# Descriptive Stats

> **Call it:** `from supplycm.statistics import descriptive_stats` · **Level:** Beginner · **You need:** basic arithmetic only

One call that describes a list of numbers: count, mean (average), median (middle value), standard deviation (how spread out), min, and max. It answers 'what does this data look like?' before you make any decision from it. Always look at your numbers before you forecast or plan with them.

**Think of it like this:** Like a medical check-up for your data: height, weight, pulse - the basic vitals.

## When to reach for it

- You just received a sales history and want a quick feel for it
- Before any forecast, to spot wild values or surprises

## Try it with supplycm

```python
from supplycm.statistics import descriptive_stats

result = descriptive_stats([120, 135, 128, 140, 122, 138, 500])
print(result)
```

You should see something like:

```text
{'mean': 183.2857, 'median': 135, 'std': 139.8698, 'variance': 19563.5714, 'min': 120, 'max': 500, 'range': 380, 'q1': 125.0, 'q3': 139.0, 'iqr': 14.0, 'count': 7}
```

The mean is pulled up well above the median by one wild day (500) - when mean and median disagree, suspect an outlier.

> **Watch out:** If the mean and median are far apart, look for outliers before trusting any average-based plan.

## Check yourself

1. What is the difference between mean and median?
2. Which is more robust to one crazy day: mean or median?
3. What does a large standard deviation tell you?

<details>
<summary>Show answers</summary>

1. Mean = add everything and divide by the count. Median = the middle value when you sort the numbers.

2. The median. One huge value can drag the mean far away, but barely moves the median.

3. The numbers swing widely around the average - demand is hard to pin down, so plans need more buffer.

</details>

## Try this now

Pull your own 14 days of sales (or invent them), run descriptive_stats, and write one sentence about what surprises you.

---
[Back to Statistics & Accuracy library](README.md) · [Z-Score →](zscore.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
