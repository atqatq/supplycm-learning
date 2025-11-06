---
title: "SES with Drift | supplycm Algorithm Library"
description: "Plain-English explanation of ses_with_drift from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, ses_with_drift, supply chain, plain english, forecasting"
---

# SES with Drift

> **Call it:** `from supplycm.forecasting import ses_with_drift` · **Level:** Intermediate · **You need:** basic arithmetic only

SES handles level; this adds a slow trend estimate on top. The result follows the level like SES but leans slightly toward where things are heading - a middle ground before committing to full Holt-style trend machinery.

**Think of it like this:** Walking while glancing at the direction you've been drifting - not committing to the trend, but not ignoring it either.

## When to reach for it

- Gentle trends where full Holt overfits noise
- Compromise forecasts between flat and trending

## Try it with supplycm

```python
from supplycm.forecasting import ses_with_drift

result = ses_with_drift([100, 105, 108, 114, 118], alpha=0.3, horizon=3)
print(result)
```

You should see something like:

```text
[118.3893, 126.748, 135.1068]
```

Forecasts rise gently - the smoothed level plus a measured drift, less twitchy than raw trend extrapolation.

## Check yourself

1. What does drift add over plain SES?
2. Why keep alpha moderate here?
3. When would you step up to Holt?

<details>
<summary>Show answers</summary>

1. Direction - the forecast stops pretending the world is flat when it plainly slopes.

2. A jumpy level plus a jumpy drift compounds noise - moderation keeps both stable.

3. When the trend itself is strong and persistent - Holt's beta tracks it explicitly.

</details>

## Try this now

Compare SES, SES-with-drift, and Holt on the same trending series; rank them by MAE and explain the podium.

---
[← Single Exponential Smoothing (SES)](single_exponential_smoothing.md) · [Back to Forecasting library](README.md) · [Holt's Linear Trend →](holt_linear_trend.md)
