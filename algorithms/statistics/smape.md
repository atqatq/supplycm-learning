---
title: "SMAPE (Symmetric MAPE) | supplycm Algorithm Library"
description: "Plain-English explanation of smape from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, smape, supply chain, plain english, statistics & accuracy"
---

# SMAPE (Symmetric MAPE)

> **Call it:** `from supplycm.statistics import smape` · **Level:** Intermediate · **You need:** basic arithmetic only

SMAPE divides the error by the average of actual and forecast instead of just the actual. That stops tiny actuals from exploding the score and caps the damage of asymmetry. It stays between 0 and 200%, making it a calmer cousin of MAPE.

**Think of it like this:** A tug-of-war scored by the rope's midpoint instead of one team's line - both sides pull fairly.

## When to reach for it

- Histories with many small or near-zero sales days
- When MAPE swings wildly because of a few tiny actuals

## Try it with supplycm

```python
from supplycm.statistics import smape

result = smape([100, 200, 2], [110, 190, 6])
print(result)
```

You should see something like:

```text
38.2173
```

Notice the third point: MAPE would scream about a 2-unit actual, but SMAPE keeps the overall number sane.

## Check yourself

1. Why 'symmetric'?
2. Is a SMAPE of 40% bad?
3. When would you still prefer plain MAPE?

<details>
<summary>Show answers</summary>

1. Actual and forecast share the denominator equally, so over- and under-forecasting of the same size score the same.

2. Depends on the product and industry - for erratic or slow movers it can be acceptable; compare against a naive baseline.

3. When your audience expects it - it remains the business standard - or when actuals are never near zero.

</details>

## Try this now

Compute MAPE and SMAPE for actuals [4, 6, 3] vs forecasts [6, 4, 9] and explain the difference in scores.

---
[← MAPE (Mean Absolute Percentage Error)](mape.md) · [Back to Statistics & Accuracy library](README.md) · [MPE (Mean Percentage Error) →](mean_percentage_error.md)
