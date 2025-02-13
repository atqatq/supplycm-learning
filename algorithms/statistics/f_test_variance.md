---
title: "F-Test for Variances | supplycm Algorithm Library"
description: "Plain-English explanation of f_test_variance from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, f_test_variance, supply chain, plain english, statistics & accuracy"
---

# F-Test for Variances

> **Call it:** `from supplycm.statistics import f_test_variance` · **Level:** Advanced · **You need:** basic arithmetic only

Sometimes the question is not whether averages differ, but whether consistency differs. The F-test divides one group's variance by the other's: a ratio near 1 means equally consistent, while a large ratio means one process is far more unpredictable than the other.

**Think of it like this:** Comparing two bus lines not on speed but on reliability: which one's arrival times swing more?

## When to reach for it

- Checking whether two suppliers are equally consistent in lead time
- Deciding if a process change affected stability rather than the average

## Try it with supplycm

```python
from supplycm.statistics import f_test_variance

result = f_test_variance([48, 52, 49, 51, 50], [30, 70, 40, 60, 20])
print(result)
```

You should see something like:

```text
0.0058
```

A large ratio - the second group is much more spread out, so plan far more buffer around it than around the first.

## Check yourself

1. An F ratio of exactly 1 means what?
2. Which group is more unpredictable if F is 9?
3. Why does higher variance force higher safety stock?

<details>
<summary>Show answers</summary>

1. Both groups have the same variance - equally consistent.

2. Whose variance sits on top of the division - the much more spread-out group.

3. You must buffer against a wider range of outcomes, so you hold more 'just in case' stock.

</details>

## Try this now

Compare lead-time variance of two imagined suppliers and state which one needs the bigger buffer.

---
[← ANOVA (One-Way F-Statistic)](anova_one_way.md) · [Back to Statistics & Accuracy library](README.md) · [One-Sample T-Statistic →](t_test_one_sample.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
