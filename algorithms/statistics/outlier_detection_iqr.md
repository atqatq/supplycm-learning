---
title: "Outlier Detection (IQR) | supplycm Algorithm Library"
description: "Plain-English explanation of outlier_detection_iqr from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, outlier_detection_iqr, supply chain, plain english, statistics & accuracy"
---

# Outlier Detection (IQR)

> **Call it:** `from supplycm.statistics import outlier_detection_iqr` · **Level:** Beginner · **You need:** basic arithmetic only

This method finds suspicious values using the interquartile range (IQR) - the box where the middle half of your data lives. Anything far below the lower fence or far above the upper fence is flagged as an outlier. It is the standard first check before you let one strange day distort a forecast.

**Think of it like this:** Like a bouncer checking heights at the door: anyone dramatically taller or shorter than the usual crowd gets a second look.

## When to reach for it

- Cleaning sales history before forecasting
- Investigating whether a demand spike was real or a data-entry mistake

## Try it with supplycm

```python
from supplycm.statistics import outlier_detection_iqr

result = outlier_detection_iqr([120, 122, 119, 121, 118, 123, 400, 120])
print(result)
```

You should see something like:

```text
[[], [400]]
```

Two lists come back: clean values, and flagged outliers - here the 400 is separated from the normal days around 120.

## Check yourself

1. What does IQR stand for and what does it measure?
2. A one-day spike that was a real promotion - should it be removed as an outlier?
3. Why clean outliers before forecasting?

<details>
<summary>Show answers</summary>

1. Interquartile range: the span between the 25th and 75th percentiles, i.e. where the middle 50% of values live.

2. Usually no. Outliers from known causes (promos) should be explained or handled separately, not silently deleted.

3. Because methods built on averages get dragged by extreme values and will over-forecast future normal days.

</details>

## Try this now

Flag outliers in [15, 16, 14, 15, 17, 15, 90] and decide: data error or real event? What would you do in each case?

---
[← Min-Max Scaling](minmax_scale.md) · [Back to Statistics & Accuracy library](README.md) · [Skewness →](skewness.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
