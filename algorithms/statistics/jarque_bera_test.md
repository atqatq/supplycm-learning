---
title: "Jarque-Bera Statistic | supplycm Algorithm Library"
description: "Plain-English explanation of jarque_bera_test from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, jarque_bera_test, supply chain, plain english, statistics & accuracy"
---

# Jarque-Bera Statistic

> **Call it:** `from supplycm.statistics import jarque_bera_test` · **Level:** Advanced · **You need:** basic arithmetic only

A shape test built from skewness (lean) and kurtosis (shockiness) together. If either is off from the normal bell curve, the statistic grows. It is a quick two-in-one diagnostic: is my data lopsided, shock-prone, or both?

**Think of it like this:** A car inspection that checks alignment and suspension in one pass - either fault shows up on the same report.

## When to reach for it

- Screening demand series before applying normal-based models
- Teaching the link between skew, kurtosis, and model risk

## Try it with supplycm

```python
from supplycm.statistics import jarque_bera_test

result = jarque_bera_test([100, 102, 98, 101, 99, 103, 97, 100, 250])
print(result)
```

You should see something like:

```text
15.4607
```

A large statistic - that spike pushes kurtosis far from normal, so beware of textbook formulas on this series.

## Check yourself

1. Which two ingredients drive the JB statistic?
2. Symmetric but shock-prone data: will JB flag it?
3. JB is high. Name two supply-chain consequences.

<details>
<summary>Show answers</summary>

1. Skewness and kurtosis - lean and shockiness of the distribution.

2. Yes - kurtosis alone can push the statistic high even with zero skew.

3. Safety stocks tuned to a normal curve will miss the real tails; percentile promises (like 95% service) will be off.

</details>

## Try this now

Compute skewness, kurtosis, then JB for one series; explain how the first two built the third.

---
[← Shapiro-Wilk Approximation](shapiro_wilk_approx.md) · [Back to Statistics & Accuracy library](README.md) · [Chi-Square Goodness of Fit →](chi_square_goodness_of_fit.md)
