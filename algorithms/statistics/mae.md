---
title: "MAE (Mean Absolute Error) | supplycm Algorithm Library"
description: "Plain-English explanation of mae from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, mae, supply chain, plain english, statistics & accuracy"
---

# MAE (Mean Absolute Error)

> **Call it:** `from supplycm.statistics import mae` · **Level:** Beginner · **You need:** basic arithmetic only

MAE is the average miss, ignoring direction: forecast 110 when actual was 100 counts as 10, whether high or low. It is the friendliest error metric to explain - 'on a typical day we are off by about this many units'. Great for everyday forecast reviews.

**Think of it like this:** Your commute app saying 'usually 10 minutes off' - a plain, honest typical-day error.

## When to reach for it

- Reporting forecast quality to non-technical teams
- Comparing two methods on the same products

## Try it with supplycm

```python
from supplycm.statistics import mae

result = mae([100, 200, 300], [110, 190, 315])
print(result)
```

You should see something like:

```text
11.6667
```

About 12 units of typical error - small enough to plan around if your order quantities are in the hundreds.

## Check yourself

1. Why take absolute values before averaging?
2. MAE of 12 on demand of 1,200 vs on demand of 15 - which is worse?
3. If MAE suddenly doubles, what do you do?

<details>
<summary>Show answers</summary>

1. So opposite errors cancel each other instead of hiding the real size of the miss.

2. The 15-unit product: 12 is 80% of typical sales, while it is just 1% for the big one. Percentages matter.

3. Investigate: something changed - season, customer mix, or the model broke. Check bias too for direction.

</details>

## Try this now

Compute MAE for two invented forecasting methods on the same history and crown a winner.

---
[← Bias (Mean Error)](bias.md) · [Back to Statistics & Accuracy library](README.md) · [MSE (Mean Squared Error) →](mse.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
