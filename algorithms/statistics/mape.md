---
title: "MAPE (Mean Absolute Percentage Error) | supplycm Algorithm Library"
description: "Plain-English explanation of mape from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, mape, supply chain, plain english, statistics & accuracy"
---

# MAPE (Mean Absolute Percentage Error)

> **Call it:** `from supplycm.statistics import mape` · **Level:** Beginner · **You need:** basic arithmetic only

MAPE expresses error as a percentage of actual sales, so it works across products of different sizes. 'We are usually 8% off' is instantly understandable and comparable between a slow seller and a fast mover. It is the most quoted forecast metric in business.

**Think of it like this:** A golf handicap: it levels the field so a beginner and a pro can be compared on relative performance.

## When to reach for it

- Comparing forecast accuracy across products with different volumes
- Setting service-level style accuracy targets (e.g., MAPE under 15%)

## Try it with supplycm

```python
from supplycm.statistics import mape

result = mape([100, 200, 400], [110, 190, 380])
print(result)
```

You should see something like:

```text
6.6667
```

Roughly 5-8% typical error - strong for most consumer products; anything under 10% is usually considered healthy. For a quick sanity check, compare your MAPE with the naive forecast’s MAPE on the same data: beating naive matters more than the absolute number.

> **Watch out:** Watch out for near-zero actuals - they blow up MAPE. Use MAE or WMAPE alongside.

## Check yourself

1. Why does MAPE break when actuals are near zero?
2. A fast mover and a slow mover both show MAPE 30%. Same pain?
3. What MAPE target is realistic for stable products vs erratic ones?

<details>
<summary>Show answers</summary>

1. Dividing by a tiny actual explodes the percentage - one unit of error on sales of 2 is 50%.

2. No - 30% of a huge product can hurt the business far more. Pair MAPE with volume-weighted views.

3. Stable staples: often under 10%. Seasonal or slow movers: 25-50% may already be good.

</details>

## Try this now

Compute MAPE for 4 weeks of two products (one big, one small) and write a two-sentence comparison for a manager.

---
[← RMSE (Root Mean Squared Error)](rmse.md) · [Back to Statistics & Accuracy library](README.md) · [SMAPE (Symmetric MAPE) →](smape.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
