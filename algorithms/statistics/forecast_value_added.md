---
title: "Forecast Value Added (FVA) | supplycm Algorithm Library"
description: "Plain-English explanation of forecast_value_added from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, forecast_value_added, supply chain, plain english, statistics & accuracy"
---

# Forecast Value Added (FVA)

> **Call it:** `from supplycm.statistics import forecast_value_added` · **Level:** Intermediate · **You need:** basic arithmetic only

FVA measures whether your whole forecasting process (with its meetings, judgments, and overrides) actually beats a naive baseline. Positive FVA = your process adds value; negative = the naive forecast would have been better. It is the gold-standard health check for S&OP forecasting.

**Think of it like this:** Asking whether the committee's edits actually improved the report - or whether the first draft was better.

## When to reach for it

- Auditing whether analyst overrides help or hurt
- Justifying (or simplifying) your forecasting process to leadership

## Try it with supplycm

```python
from supplycm.statistics import forecast_value_added

result = forecast_value_added([100, 200, 300], [95, 210, 290], [100, 100, 100])
print(result)
```

You should see something like:

```text
34.4444
```

A positive FVA - the real forecast beats the naive baseline on percentage error, so the process earns its complexity.

## Check yourself

1. FVA is -3%. What should leadership consider?
2. Which naive baseline is usually used?
3. Who should see FVA regularly?

<details>
<summary>Show answers</summary>

1. The process destroys value vs a naive forecast - simplify, or find which step (override? data?) hurts.

2. Often 'no change from last period'; seasonal products may use 'same period last year'.

3. The S&OP team and executives - it is the cheapest way to keep the process honest.

</details>

## Try this now

Take any forecast plus a naive copy; compute FVA and write a one-line verdict for the process owner.

---
[← MASE (Mean Absolute Scaled Error)](mase.md) · [Back to Statistics & Accuracy library](README.md) · [Diebold-Mariano Test →](diebold_mariano_test.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
