---
title: "Kolmogorov-Smirnov Test (One Sample) | supplycm Algorithm Library"
description: "Plain-English explanation of kolmogorov_smirnov_test from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, kolmogorov_smirnov_test, supply chain, plain english, statistics & accuracy"
---

# Kolmogorov-Smirnov Test (One Sample)

> **Call it:** `from supplycm.statistics import kolmogorov_smirnov_test` · **Level:** Advanced · **You need:** basic arithmetic only

KS compares the whole shape of your data to a reference pattern - it walks along the sorted values and measures the biggest gap between what you have and what you'd expect. One big number decides: small gap = shapes match, big gap = they do not.

**Think of it like this:** Overlaying two silhouettes and measuring the widest gap between them.

## When to reach for it

- Checking demand shape against a reference distribution without binning
- Verifying simulation outputs resemble the real history

## Try it with supplycm

```python
from supplycm.statistics import kolmogorov_smirnov_test

result = kolmogorov_smirnov_test([10, 12, 11, 13, 12, 11, 30, 10, 12, 11])
print(result)
```

You should see something like:

```text
0.4133
```

The statistic reflects the largest shape gap - here the 30 stretches the pattern away from a smooth bell.

## Check yourself

1. What makes KS different from chi-square?
2. KS statistic is large. Conclusion?
3. When is a shape check more important than an average check?

<details>
<summary>Show answers</summary>

1. KS works on the full ordered shape and needs no arbitrary category bins.

2. The data's overall shape does not match the reference - dig into where the gap opens.

3. When tails drive decisions - safety stock, service levels, disaster planning.

</details>

## Try this now

Test a symmetric series and then the same series with one value doubled; watch the statistic respond.

---
[← Chi-Square Goodness of Fit](chi_square_goodness_of_fit.md) · [Back to Statistics & Accuracy library](README.md) · [KS Test (Two Samples) →](kolmogorov_smirnov_two_sample.md)
