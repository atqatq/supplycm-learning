---
title: "Moving Average Smoothing | supplycm Algorithm Library"
description: "Plain-English explanation of moving_average_smooth from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, moving_average_smooth, supply chain, plain english, statistics & accuracy"
---

# Moving Average Smoothing

> **Call it:** `from supplycm.statistics import moving_average_smooth` · **Level:** Beginner · **You need:** basic arithmetic only

A moving average replaces each point with the average of its neighbors, smoothing out day-to-day noise so the underlying trend shows. It is the simplest way to see the forest for the trees in a jittery sales chart. Bigger windows give smoother (but slower to react) lines.

**Think of it like this:** Squinting at a noisy chart: the wiggles blur away and the general direction becomes obvious.

## When to reach for it

- Presenting a trend to management without daily noise
- As a first cleaning step before more advanced smoothing

## Try it with supplycm

```python
from supplycm.statistics import moving_average_smooth

result = moving_average_smooth([40, 55, 42, 58, 41, 57, 43], window=3)
print(result)
```

You should see something like:

```text
[47.5, 45.6667, 51.6667, 47.0, 52.0, 47.0, 50.0]
```

The zigzag flattens into values near 46 - the underlying level is stable even though individual days bounce.

## Check yourself

1. What happens if you increase the window from 3 to 12?
2. Why do the early positions lack a full average?
3. Name one risk of over-smoothing.

<details>
<summary>Show answers</summary>

1. The line gets smoother but reacts more slowly to real changes.

2. At the start there are not enough neighbors yet to fill a full window.

3. You can hide real turning points until it is too late to react.

</details>

## Try this now

Smooth a choppy 12-point series with windows 3 and 5; describe what changes.

---
[← Bootstrap Confidence Interval](bootstrap_confidence_interval.md) · [Back to Statistics & Accuracy library](README.md) · [Exponential Smoothing (Statistics) →](exponential_smooth.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
