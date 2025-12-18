---
title: "Tracking Signal | supplycm Algorithm Library"
description: "Plain-English explanation of tracking_signal from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, tracking_signal, supply chain, plain english, forecasting"
---

# Tracking Signal

> **Call it:** `from supplycm.forecasting import tracking_signal` · **Level:** Intermediate · **You need:** basic arithmetic only

A forecast alarm system: it accumulates forecast errors and divides by their typical size. Wandering near zero means errors cancel (healthy); marching persistently toward +4 or -4 means systematic bias - time to re-fit. It turns silent drift into a beeping dashboard.

**Think of it like this:** A smoker's detector for forecast bias: it doesn't measure each puff, it notices the ROOM is filling up.

## When to reach for it

- Monitoring live forecasts between re-fits
- Deciding WHEN a forecast deserves human attention

## Try it with supplycm

```python
from supplycm.forecasting import tracking_signal

result = tracking_signal(actual=[100, 105, 112, 118, 125], forecast=[100, 103, 107, 111, 115])
print(result)
```

You should see something like:

```text
[0.0, 2.0, 3.0, 4.0, 5.0]
```

The signal climbs period by period - actuals keep beating the forecast, and the drift toward the alarm band is visible in advance.

## Check yourself

1. What does a signal of +5 mean?
2. Why divide cumulative error by mean absolute error?
3. Signal crosses the threshold. First move?

<details>
<summary>Show answers</summary>

1. Persistent under-forecasting - actuals exceeded forecasts repeatedly in the same direction.

2. To scale the alarm: +4 means 'bias of 4 typical errors' - comparable across items of any size.

3. Investigate causes (new customer? promo? price change?) before re-fitting - the signal detects bias, not its story.

</details>

## Try this now

Simulate 12 weeks where actuals run +3 above forecast; chart the signal's climb and time the alarm.

---
[← Bottom-Up Reconciliation](bottom_up_reconciliation.md) · [Back to Forecasting library](README.md) · [Brier Score →](brier_score.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
