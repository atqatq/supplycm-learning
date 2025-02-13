---
title: "Tracking Signal Threshold Check | supplycm Algorithm Library"
description: "Plain-English explanation of tracking_signal_threshold from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, tracking_signal_threshold, supply chain, plain english, statistics & accuracy"
---

# Tracking Signal Threshold Check

> **Call it:** `from supplycm.statistics import tracking_signal_threshold` · **Level:** Beginner · **You need:** basic arithmetic only

A tracking signal watches whether your forecast is persistently too high or too low. This helper takes the signal value and simply answers True (inside the healthy band, typically -4 to +4) or False (drifting out of control). It turns a running number into a yes/no alarm for your planning review.

**Think of it like this:** A smoke detector: it does not explain the fire, it just beeps the moment smoke crosses the safe line.

## When to reach for it

- Automating forecast health checks in a weekly review
- Deciding when a forecast needs re-fitting rather than small nudges

## Try it with supplycm

```python
from supplycm.statistics import tracking_signal_threshold

result = tracking_signal_threshold(6.5)
print(result)
```

You should see something like:

```text
True
```

False - 6.5 is outside the -4 to +4 band, so the forecast has been persistently biased and needs attention.

## Check yourself

1. A tracking signal of +5 means the forecast has been doing what?
2. Why is a constant small error worse than alternating errors?
3. What is the first response when the alarm fires?

<details>
<summary>Show answers</summary>

1. Persistently UNDER-forecasting - actuals keep beating it in the same direction.

2. Alternating errors cancel out; a constant push in one direction compounds into big inventory or service mistakes.

3. Investigate for a level shift (new customer, promo, price change) and re-fit or adjust the forecast.

</details>

## Try this now

Simulate 10 weeks where actuals beat the forecast by 3 units every week; confirm the signal eventually crosses the threshold.

---
[← Two-Sample T-Statistic](t_test_two_sample.md) · [Back to Statistics & Accuracy library](README.md) · [Bias (Mean Error) →](bias.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
