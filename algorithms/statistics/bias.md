---
title: "Bias (Mean Error) | supplycm Algorithm Library"
description: "Plain-English explanation of bias from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, bias, supply chain, plain english, statistics & accuracy"
---

# Bias (Mean Error)

> **Call it:** `from supplycm.statistics import bias` · **Level:** Beginner · **You need:** basic arithmetic only

Bias is the average of (actual minus forecast). Positive means you under-forecast too often; negative means you over-forecast. Unlike MAPE, bias shows direction - it tells you WHICH way you are consistently wrong, not just how wrong.

**Think of it like this:** A basketball player who always misses 10 cm to the left: the average error is the same as random misses, but the direction reveals the fixable problem.

## When to reach for it

- Checking whether a forecast systematically over- or under-predicts
- Monthly forecast reviews where direction matters more than size

## Try it with supplycm

```python
from supplycm.statistics import bias

result = bias([100, 110, 120, 130], [95, 100, 110, 120])
print(result)
```

You should see something like:

```text
-8.75
```

A positive bias - every forecast landed below the actual, so the planner keeps being surprised by demand they should have seen coming. Read bias TOGETHER with MAPE: bias gives the direction of the miss, MAPE gives its typical size.

> **Watch out:** Track bias every month - a small persistent bias costs more than occasional big misses.

## Check yourself

1. Bias of -8 means the forecast has been doing what?
2. Can errors be large while bias is 0?
3. You fix a positive bias by just adding +5 to every forecast. What could go wrong?

<details>
<summary>Show answers</summary>

1. Over-forecasting by 8 units on average - you are planning for more demand than shows up.

2. Yes - big misses in opposite directions cancel out. That is why you track bias AND a size metric like MAPE.

3. The underlying pattern is still unexplained; the offset may not hold as conditions change. Fix causes, not symptoms.

</details>

## Try this now

Take any 6 weeks of invented actuals/forecasts, compute bias, and state which way the planner should adjust.

---
[← Tracking Signal Threshold Check](tracking_signal_threshold.md) · [Back to Statistics & Accuracy library](README.md) · [MAE (Mean Absolute Error) →](mae.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
