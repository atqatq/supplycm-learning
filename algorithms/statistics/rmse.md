---
title: "RMSE (Root Mean Squared Error) | supplycm Algorithm Library"
description: "Plain-English explanation of rmse from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, rmse, supply chain, plain english, statistics & accuracy"
---

# RMSE (Root Mean Squared Error)

> **Call it:** `from supplycm.statistics import rmse` · **Level:** Intermediate · **You need:** basic arithmetic only

RMSE is the square root of MSE. It punishes big misses like MSE does, but expresses the answer in the original units, so 'RMSE = 25 units' actually means something to a planner. It is the default error metric in many forecasting tools.

**Think of it like this:** Like MSE wearing a translator badge: same harsh scoring, but it speaks planner language again.

## When to reach for it

- Standard forecast-quality reporting across teams
- Comparing models where large misses must stay visible

## Try it with supplycm

```python
from supplycm.statistics import rmse

result = rmse([100, 200, 300], [110, 190, 320])
print(result)
```

You should see something like:

```text
14.1421
```

Roughly 14 units typical error, weighted toward the worst miss - between MAE and the raw squared penalty.

## Check yourself

1. Why take a square root at all?
2. Which is always bigger: MAE or RMSE?
3. RMSE is 3x MAE. What does that reveal?

<details>
<summary>Show answers</summary>

1. Squaring distorts units; the root brings errors back to 'units of demand' so people can act on them.

2. RMSE is never smaller - the extra weight on big errors keeps it at or above MAE.

3. Errors are lumpy - a few big misses dominate. Investigate those days rather than the average day.

</details>

## Try this now

Compute MAE and RMSE for [10,10,10,50] vs [0,20,20,20] error patterns (same MAE, different RMSE) and explain.

---
[← MSE (Mean Squared Error)](mse.md) · [Back to Statistics & Accuracy library](README.md) · [MAPE (Mean Absolute Percentage Error) →](mape.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
