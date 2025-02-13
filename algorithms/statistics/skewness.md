---
title: "Skewness | supplycm Algorithm Library"
description: "Plain-English explanation of skewness from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, skewness, supply chain, plain english, statistics & accuracy"
---

# Skewness

> **Call it:** `from supplycm.statistics import skewness` · **Level:** Intermediate · **You need:** basic arithmetic only

Skewness tells you which side your data leans. Zero means a symmetric shape; positive skew means a long tail of occasional big values; negative skew means a long tail of small ones. Demand data is often positively skewed - many ordinary days, a few huge ones.

**Think of it like this:** Imagine a dog's tail: if the tail drags to the right, the data is right-skewed.

## When to reach for it

- Checking if you can safely use averages (skewed data prefers medians)
- Understanding spare-parts or slow-mover demand, where many small days and rare big days mix

## Try it with supplycm

```python
from supplycm.statistics import skewness

result = skewness([10, 11, 12, 10, 11, 45])
print(result)
```

You should see something like:

```text
1.7774
```

A positive skew - the ordinary days cluster low while one big day stretches the tail to the right.

## Check yourself

1. Positive skew means the tail points which way?
2. For strongly skewed demand, is mean or median the better 'typical day'?
3. Give a real product likely to have positive demand skew.

<details>
<summary>Show answers</summary>

1. To the right - toward the occasional large values.

2. The median - the mean gets pulled by the tail.

3. Umbrellas: steady low sales with rare storm-day surges.

</details>

## Try this now

Sketch (on paper) a demand pattern with negative skew and name a product that behaves that way.

---
[← Outlier Detection (IQR)](outlier_detection_iqr.md) · [Back to Statistics & Accuracy library](README.md) · [Kurtosis →](kurtosis.md)

*New to this topic? Start with the core lesson first: [01_what_is_supply_chain.md](../../modules/01_what_is_supply_chain.md).*
