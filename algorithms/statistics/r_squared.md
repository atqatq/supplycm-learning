---
title: "R-Squared | supplycm Algorithm Library"
description: "Plain-English explanation of r_squared from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, r_squared, supply chain, plain english, statistics & accuracy"
---

# R-Squared

> **Call it:** `from supplycm.statistics import r_squared` · **Level:** Intermediate · **You need:** basic arithmetic only

R-squared says how much of the movement in your actuals your forecast or line managed to explain, from 0 to 1. An R-squared of 0.8 means your model's guesses track 80% of the up-and-down pattern. It compares a model against the lazy baseline of 'just predict the average'.

**Think of it like this:** Like grading how well a shadow follows the person casting it: 1 = perfect silhouette, 0 = shadow ignores them.

## When to reach for it

- Judging how well a fitted line or model tracks history
- Comparing two candidate models on the same data

## Try it with supplycm

```python
from supplycm.statistics import r_squared

result = r_squared([10, 20, 30, 40], [11, 19, 31, 39])
print(result)
```

You should see something like:

```text
0.992
```

Very close to 1 - the forecast almost perfectly follows the actual pattern.

## Check yourself

1. R-squared of 0 means what?
2. Is a high R-squared alone proof the forecast is good?
3. Forecast A: R-squared 0.9. Forecast B: 0.4. Which tracks history better?

<details>
<summary>Show answers</summary>

1. The model explains nothing beyond just predicting the overall average.

2. Not alone - it can look great on history and still fail forward. Always also check out-of-sample error.

3. A - it follows 90% of the pattern vs 40%.

</details>

## Try this now

For the pairs ([5,10,15],[6,9,16]) and ([5,10,15],[9,10,11]), compute R-squared and say which fit tracks better.

---
[← Spearman Correlation](spearman_correlation.md) · [Back to Statistics & Accuracy library](README.md) · [Coefficient of Determination →](coefficient_of_determination.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
