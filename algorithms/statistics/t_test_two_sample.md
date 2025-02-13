---
title: "Two-Sample T-Statistic | supplycm Algorithm Library"
description: "Plain-English explanation of t_test_two_sample from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, t_test_two_sample, supply chain, plain english, statistics & accuracy"
---

# Two-Sample T-Statistic

> **Call it:** `from supplycm.statistics import t_test_two_sample` · **Level:** Intermediate · **You need:** basic arithmetic only

Compares the averages of two groups and returns a t-statistic - near 0 means the groups are indistinguishable, large means one is genuinely higher or lower than the other. Perfect for A-versus-B questions: two packers, two carriers, two promotions.

**Think of it like this:** Tasting two coffees blind many times and asking: is there a real difference, or am I imagining it?

## When to reach for it

- Comparing output of two workers, machines, or shifts
- Checking whether a pilot change beat the old process

## Try it with supplycm

```python
from supplycm.statistics import t_test_two_sample

result = t_test_two_sample([30, 32, 31, 29, 33], [38, 40, 39, 41, 40])
print(result)
```

You should see something like:

```text
-9.8649
```

A clearly negative, large t - the first group's average sits far below the second's, a real difference, not noise.

## Check yourself

1. t = -0.2 vs t = -5.2: which shows a clearer difference?
2. Name the assumptions behind trusting this test.
3. You pilot a new picking method. Half the team uses it. What do you compare?

<details>
<summary>Show answers</summary>

1. The -5.2 - far from 0 means the gap is much larger than noise could explain.

2. Reasonably well-behaved (not wildly skewed) data, few outliers, and enough points per group.

3. Picks-per-hour of both groups with a two-sample test - and also check consistency, not just the average.

</details>

## Try this now

Invent before/after defect counts for a process change and test whether the change truly moved the average.

---
[← One-Sample T-Statistic](t_test_one_sample.md) · [Back to Statistics & Accuracy library](README.md) · [Tracking Signal Threshold Check →](tracking_signal_threshold.md)
