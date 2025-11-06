---
title: "Dampened Trend Method | supplycm Algorithm Library"
description: "Plain-English explanation of dampened_trend from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, dampened_trend, supply chain, plain english, forecasting"
---

# Dampened Trend Method

> **Call it:** `from supplycm.forecasting import dampened_trend` · **Level:** Intermediate · **You need:** basic arithmetic only

Holt with brakes: a damping factor (phi) shrinks the trend each period forward - +10, then +9.5, then +9... Real trends fade; this method bakes that humility in. Empirically one of the most reliable forecasters across industries.

**Think of it like this:** A ball rolling downhill: fast at first, slower as friction wins - the slope doesn't continue forever.

## When to reach for it

- Medium-to-long horizons on trending data
- Any trend forecast that must survive management scrutiny

## Try it with supplycm

```python
from supplycm.forecasting import dampened_trend

result = dampened_trend([100, 110, 122, 131, 141], alpha=0.5, beta=0.1, phi=0.9, horizon=4)
print(result)
```

You should see something like:

```text
[145.7388, 152.203, 158.0209, 163.2569]
```

Forecasts rise with a shrinking step each period - the +10 trend decays toward flatness instead of rocketing.

## Check yourself

1. What does phi = 0.9 vs 0.5 change?
2. Why is damping so often the right call?
3. Phi = 1 recovers what?

<details>
<summary>Show answers</summary>

1. 0.9 lets the trend run longer; 0.5 kills it fast - the dial from Holt to near-SES.

2. Untamed trends over-forecast dramatically at longer horizons; damping costs little when trends persist and saves a lot when they fade.

3. Plain Holt - no damping at all.

</details>

## Try this now

Forecast 8 periods ahead with phi 1.0 vs 0.85 on the same series and show the divergence to management.

---
[← Holt's Linear Trend](holt_linear_trend.md) · [Back to Forecasting library](README.md) · [Holt-Winters (Triple Smoothing) →](holt_winters.md)
