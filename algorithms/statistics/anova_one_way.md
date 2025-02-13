---
title: "ANOVA (One-Way F-Statistic) | supplycm Algorithm Library"
description: "Plain-English explanation of anova_one_way from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, anova_one_way, supply chain, plain english, statistics & accuracy"
---

# ANOVA (One-Way F-Statistic)

> **Call it:** `from supplycm.statistics import anova_one_way` · **Level:** Intermediate · **You need:** basic arithmetic only

ANOVA asks whether several groups really differ in their average, or whether the differences are just noise. It returns an F-statistic: near 1 means the group differences look like ordinary noise, while a big F means the groups genuinely behave differently. Use it to compare, say, demand across regions or output across shifts.

**Think of it like this:** A referee deciding whether three bakers' bread weights truly differ, or whether any difference could be luck.

## When to reach for it

- Comparing average sales across 3+ stores, regions, or promotions
- Checking whether two machine shifts produce equal-quality output

## Try it with supplycm

```python
from supplycm.statistics import anova_one_way

result = anova_one_way([[20, 22, 19, 21], [34, 36, 33, 35], [50, 52, 49, 51]])
print(result)
```

You should see something like:

```text
540.8
```

A very large F - the groups differ far more than noise inside each group could explain, so treat them as genuinely different.

## Check yourself

1. An F-statistic near 1 suggests what?
2. Why not just run several two-group tests instead?
3. What should you check before trusting a big F?

<details>
<summary>Show answers</summary>

1. The between-group differences are about what noise alone would produce - probably no real difference.

2. Repeated tests pile up false alarms; ANOVA compares all groups in one fair test.

3. That each group has enough data and no wild outliers - F is sensitive to extremes.

</details>

## Try this now

Build three groups where two are identical in average and one differs; run ANOVA and interpret the F.

---
[← Exponential Smoothing (Statistics)](exponential_smooth.md) · [Back to Statistics & Accuracy library](README.md) · [F-Test for Variances →](f_test_variance.md)
