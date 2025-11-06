---
title: "Moving Median Filter | supplycm Algorithm Library"
description: "Plain-English explanation of moving_median_filter from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, moving_median_filter, supply chain, plain english, forecasting"
---

# Moving Median Filter

> **Call it:** `from supplycm.forecasting import moving_median_filter` · **Level:** Intermediate · **You need:** basic arithmetic only

The moving average's tougher sibling: take the MEDIAN (middle value) of the last N points instead of the mean. One wild spike cannot drag a median - it simply gets outvoted. Use it when your history has outlier days you cannot trust or explain.

**Think of it like this:** Nine neighbors and one billionaire: the average street 'income' is absurd, the median neighbor still lives like your street.

## When to reach for it

- Cleaning histories with spikes before forecasting
- Demand streams with occasional data errors

## Try it with supplycm

```python
from supplycm.forecasting import moving_median_filter

result = moving_median_filter([40, 42, 400, 43, 41, 44], window=3)
print(result)
```

You should see something like:

```text
[41.0, 42.0, 43.0, 43.0, 43.0, 42.5]
```

The 400 barely registers in the output - the median outvoted it; a mean would have been dragged violently.

## Check yourself

1. Why is the median robust to outliers?
2. Median vs mean on clean data - any difference?
3. What does a large window cost here?

<details>
<summary>Show answers</summary>

1. It depends on the middle ORDER, not the magnitude - one extreme value cannot pull it.

2. Barely - on well-behaved data they nearly agree; on spiky data they diverge dramatically.

3. Responsiveness - the median vote grows sluggish as the window widens.

</details>

## Try this now

Filter a series containing two consecutive spikes; compare mean vs median outputs and note which recovers faster.

---
[← Rolling Mean Forecast](rolling_mean_forecast.md) · [Back to Forecasting library](README.md) · [Drift Method →](drift_method.md)
