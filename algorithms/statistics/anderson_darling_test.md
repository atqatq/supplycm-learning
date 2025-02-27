---
title: "Anderson-Darling Statistic | supplycm Algorithm Library"
description: "Plain-English explanation of anderson_darling_test from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, anderson_darling_test, supply chain, plain english, statistics & accuracy"
---

# Anderson-Darling Statistic

> **Call it:** `from supplycm.statistics import anderson_darling_test` · **Level:** Advanced · **You need:** basic arithmetic only

Checks whether your data plausibly follows a bell-curve (normal) shape, paying special attention to the tails. A small statistic means 'yes, bell-ish'; a big one means the shape is off. Many inventory formulas assume a normal curve, so this is the pre-flight check.

**Think of it like this:** A dressmaker checking whether a client really has 'standard' proportions before cutting a standard pattern.

## When to reach for it

- Before using safety-stock formulas that assume normal demand
- Auditing whether lead times or demand are surprisingly non-normal

## Try it with supplycm

```python
from supplycm.statistics import anderson_darling_test

result = anderson_darling_test([50, 52, 48, 51, 49, 53, 47, 50, 52, 300])
print(result)
```

You should see something like:

```text
3.0347
```

A large statistic - that 300 wrecks the bell shape, so normal-based formulas would mislead here.

## Check yourself

1. Why do tails matter so much in supply chains?
2. Data fails the normality check. Now what?
3. Is a small statistic a guarantee the data is normal?

<details>
<summary>Show answers</summary>

1. Stockouts and surpluses live in the tails - the rare days. Get the tails wrong and your buffers are wrong.

2. Use methods that do not assume a bell curve - simulations, bootstrap intervals, or non-normal distributions.

3. No - just 'no evidence against it'. Real demand is often at least a bit lumpy.

</details>

## Try this now

Test 20 values you sample around a stable average, then add one extreme value and see how the statistic reacts.

---
[← Diebold-Mariano Test](diebold_mariano_test.md) · [Back to Statistics & Accuracy library](README.md) · [Shapiro-Wilk Approximation →](shapiro_wilk_approx.md)
