---
title: "Simple Moving Average (SMA) | supplycm Algorithm Library"
description: "Plain-English explanation of simple_moving_average from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, simple_moving_average, supply chain, plain english, forecasting"
---

# Simple Moving Average (SMA)

> **Call it:** `from supplycm.forecasting import simple_moving_average` · **Level:** Beginner · **You need:** basic arithmetic only

Average the last N periods and use that as the forecast - then slide the window forward. Recent history speaks, older history falls silent. The window size is the personality dial: small windows react fast and jitter; large windows stay calm and lag.

**Think of it like this:** Looking at the view through a camera that averages the last N frames - steady, but a fast turn blurs into lag.

## When to reach for it

- Stable demand with moderate noise
- Quick smoothing for reports and dashboards

## Try it with supplycm

```python
from supplycm.forecasting import simple_moving_average

result = simple_moving_average([40, 45, 42, 50, 48, 55], window=3)
print(result)
```

You should see something like:

```text
[None, None, 42.3333, 45.6667, 46.6667, 51.0]
```

Each output averages the prior 3 points - the first slots stay empty until a full window exists.

## Check yourself

1. Window 3 vs window 12 - what changes?
2. Why do early slots come up empty?
3. How does SMA lag a rising trend?

<details>
<summary>Show answers</summary>

1. 3 reacts quickly with jitter; 12 is smooth but slow to notice real shifts.

2. A full window of history does not exist yet - honesty about what the average could know.

3. It averages past values including lower ones, so it sits below the current level - always trailing.

</details>

## Try this now

Compute window-3 and window-5 forecasts on the same 10 points; identify the period where they disagree most.

---
[← Average Method](average_method.md) · [Back to Forecasting library](README.md) · [Weighted Moving Average →](weighted_moving_average.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
