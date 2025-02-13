---
title: "Adjusted R-Squared | supplycm Algorithm Library"
description: "Plain-English explanation of adjusted_r_squared from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, adjusted_r_squared, supply chain, plain english, statistics & accuracy"
---

# Adjusted R-Squared

> **Call it:** `from supplycm.statistics import adjusted_r_squared` · **Level:** Advanced · **You need:** basic arithmetic only

Every extra factor you throw into a model makes plain R-squared look better, even when the factor is useless. Adjusted R-squared adds a penalty for each factor, so it only rises if the new factor genuinely helps. Use it when comparing models with different numbers of variables.

**Think of it like this:** Like grading on a curve that subtracts points for every hint sheet a student brings - only real skill raises the score.

## When to reach for it

- Choosing between a simple and a fancy model fairly
- Preventing 'kitchen sink' models stuffed with useless drivers

## Try it with supplycm

```python
from supplycm.statistics import adjusted_r_squared

result = adjusted_r_squared(0.85, 30, 5)
print(result)
```

You should see something like:

```text
0.8187
```

With 30 observations and 5 factors, the adjusted value stays close to the raw 0.85 - here the sample is big enough to support 5 factors.

## Check yourself

1. Why does plain R-squared never decrease when you add a factor?
2. You add a factor and adjusted R-squared drops. What does that tell you?
3. When do R-squared and adjusted R-squared converge?

<details>
<summary>Show answers</summary>

1. It mechanically rewards any extra variable, even noise. That is why the adjusted version exists.

2. The factor was not worth its complexity - drop it.

3. When the sample size is large relative to the number of factors.

</details>

## Try this now

Compute adjusted R-squared for (0.85, n=30, p=5) and (0.85, n=8, p=5). Which model would you trust and why?

---
[← Coefficient of Determination](coefficient_of_determination.md) · [Back to Statistics & Accuracy library](README.md) · [Confidence Interval for a Mean →](confidence_interval_mean.md)
