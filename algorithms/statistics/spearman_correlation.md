---
title: "Spearman Correlation | supplycm Algorithm Library"
description: "Plain-English explanation of spearman_correlation from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, spearman_correlation, supply chain, plain english, statistics & accuracy"
---

# Spearman Correlation

> **Call it:** `from supplycm.statistics import spearman_correlation` · **Level:** Intermediate · **You need:** basic arithmetic only

Spearman correlation compares rankings instead of raw values. If high values of X line up with high ranks of Y, you get close to +1. It catches 'moves together in order' relationships even when the exact amounts are wildly different, and it is not fooled by one huge outlier.

**Think of it like this:** Two judges at a talent show who score contestants with totally different point systems - but if their ranking order matches, Spearman says they agree.

## When to reach for it

- Correlating rank-like data (supplier preference order vs delivery rank)
- When outliers would distort a normal correlation

## Try it with supplycm

```python
from supplycm.statistics import spearman_correlation

result = spearman_correlation([10, 20, 30, 4000], [1, 2, 3, 5])
print(result)
```

You should see something like:

```text
1.0
```

Spearman is +1 - even though 4000 is an enormous outlier, the ranks line up perfectly.

## Check yourself

1. When would you prefer Spearman over normal correlation?
2. Two series ranked exactly opposite get which Spearman value?
3. A store's daily sales rank correlates 0.95 with daily visitors' rank. What should management consider?

<details>
<summary>Show answers</summary>

1. When only the order matters, or when outliers would distort the raw-value correlation.

2. -1.

3. Foot traffic drives sales - so forecasting visitors may help forecast sales.

</details>

## Try this now

Take the ranks of 5 products by profit and by units sold; compute Spearman and interpret it.

---
[← Correlation](correlation.md) · [Back to Statistics & Accuracy library](README.md) · [R-Squared →](r_squared.md)
