---
title: "Shapiro-Wilk Approximation | supplycm Algorithm Library"
description: "Plain-English explanation of shapiro_wilk_approx from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, shapiro_wilk_approx, supply chain, plain english, statistics & accuracy"
---

# Shapiro-Wilk Approximation

> **Call it:** `from supplycm.statistics import shapiro_wilk_approx` · **Level:** Advanced · **You need:** basic arithmetic only

Another bell-curve check, famous for being sensitive even with small samples. It returns a statistic that drops when your data strays from normal. With only 10-30 observations - common for new products - this is often the most practical shape test.

**Think of it like this:** A quick taste test that can judge a small spoonful, not just the whole pot.

## When to reach for it

- Small samples where bigger tests lack power
- Checking a new product's first months of demand before setting buffers

## Try it with supplycm

```python
from supplycm.statistics import shapiro_wilk_approx

result = shapiro_wilk_approx([50, 52, 48, 51, 49, 53, 47, 50, 52, 51])
print(result)
```

You should see something like:

```text
0.4327
```

A statistic close to 1 - these values could easily come from a normal bell curve, so standard formulas are safe to try.

## Check yourself

1. What does a statistic near 1 suggest?
2. Why does small-sample sensitivity matter in supply chains?
3. Data is skewed right. Which safety-stock approach fits better?

<details>
<summary>Show answers</summary>

1. The data looks consistent with a normal bell curve.

2. New SKUs and short histories are everywhere; you still need a shape check with 12 data points.

3. One that respects the skew - e.g., simulation or quantile-based buffers - rather than plain normal formulas.

</details>

## Try this now

Run it on a skewed series of 15 points and on a symmetric one; compare which looks more 'bell-shaped'.

---
[← Anderson-Darling Statistic](anderson_darling_test.md) · [Back to Statistics & Accuracy library](README.md) · [Jarque-Bera Statistic →](jarque_bera_test.md)
