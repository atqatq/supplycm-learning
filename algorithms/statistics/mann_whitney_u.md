---
title: "Mann-Whitney U | supplycm Algorithm Library"
description: "Plain-English explanation of mann_whitney_u from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, mann_whitney_u, supply chain, plain english, statistics & accuracy"
---

# Mann-Whitney U

> **Call it:** `from supplycm.statistics import mann_whitney_u` · **Level:** Advanced · **You need:** basic arithmetic only

A rank-based contest between two groups: pool all values, rank them, and see whether one group dominates the top ranks. It asks 'does one group tend to be bigger?' without caring about averages or bell curves - ideal for skewed demand or small samples.

**Think of it like this:** Two teams of runners finish a race; you ignore their exact times and just count who places higher overall.

## When to reach for it

- Comparing two skewed demand histories (e.g., promo vs normal weeks)
- Small samples where t-tests feel shaky

## Try it with supplycm

```python
from supplycm.statistics import mann_whitney_u

result = mann_whitney_u([12, 13, 11, 14, 12], [30, 31, 29, 32, 30])
print(result)
```

You should see something like:

```text
[0.0, 25.0]
```

The U values show one group sweeping the high ranks - group 2's values sit almost entirely above group 1's.

## Check yourself

1. What does U actually count?
2. Why use ranks instead of raw values?
3. U strongly favors group B. Verdict?

<details>
<summary>Show answers</summary>

1. Ranks: how often a value from one group beats a value from the other.

2. Outliers and skew distort averages; ranks only care about order, which is more robust.

3. B tends to run higher - plan differently for it (more capacity, bigger buffers, separate forecast).

</details>

## Try this now

Compare promo-week vs regular-week sales (5 each) with Mann-Whitney and state the verdict in one sentence.

---
[← KS Test (Two Samples)](kolmogorov_smirnov_two_sample.md) · [Back to Statistics & Accuracy library](README.md) · [Wilcoxon Signed-Rank →](wilcoxon_signed_rank.md)
