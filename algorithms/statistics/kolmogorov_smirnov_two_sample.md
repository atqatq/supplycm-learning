---
title: "KS Test (Two Samples) | supplycm Algorithm Library"
description: "Plain-English explanation of kolmogorov_smirnov_two_sample from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, kolmogorov_smirnov_two_sample, supply chain, plain english, statistics & accuracy"
---

# KS Test (Two Samples)

> **Call it:** `from supplycm.statistics import kolmogorov_smirnov_two_sample` · **Level:** Advanced · **You need:** basic arithmetic only

Asks whether two batches of data come from the same overall pattern - not just the same average. It compares their sorted shapes and reports the biggest gap. Use it to check whether this month's demand behaves like last year's, beyond the mean.

**Think of it like this:** Comparing two fingerprints, not just heights: do the whole patterns match, ridge by ridge?

## When to reach for it

- Checking if this quarter's demand pattern differs from last year's
- Validating that simulated demand mimics real demand

## Try it with supplycm

```python
from supplycm.statistics import kolmogorov_smirnov_two_sample

result = kolmogorov_smirnov_two_sample([10, 12, 11, 13, 12], [30, 28, 32, 29, 31])
print(result)
```

You should see something like:

```text
1.0
```

A large gap statistic - the two batches barely overlap, so they clearly behave differently.

## Check yourself

1. What question does the two-sample KS answer?
2. Two batches share an average but KS is large. What is going on?
3. Before trusting a simulation for planning, what should you run?

<details>
<summary>Show answers</summary>

1. 'Could these two batches come from the same underlying pattern?' - about whole shape, not just averages.

2. Their spread or shape differs - e.g., one is calm, one is spiky - which averages hide.

3. A two-sample KS (or similar shape check) between simulated and real demand.

</details>

## Try this now

Generate two demand patterns with equal averages but different spread; confirm KS flags them.

---
[← Kolmogorov-Smirnov Test (One Sample)](kolmogorov_smirnov_test.md) · [Back to Statistics & Accuracy library](README.md) · [Mann-Whitney U →](mann_whitney_u.md)
