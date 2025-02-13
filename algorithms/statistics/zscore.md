---
title: "Z-Score | supplycm Algorithm Library"
description: "Plain-English explanation of zscore from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, zscore, supply chain, plain english, statistics & accuracy"
---

# Z-Score

> **Call it:** `from supplycm.statistics import zscore` · **Level:** Beginner · **You need:** basic arithmetic only

A z-score says how many 'usual steps' (standard deviations) a value sits away from the average. Around 0 means perfectly typical, +2 means unusually high, -2 means unusually low. It turns raw numbers into a common 'surprise scale' you can compare across products.

**Think of it like this:** Like a growth chart at the doctor's: it says how far a child is from the typical height for their age.

## When to reach for it

- Flagging days whose sales were shockingly high or low
- Comparing a spike in coffee sales with a spike in mug sales that have totally different volumes

## Try it with supplycm

```python
from supplycm.statistics import zscore

result = zscore([40, 42, 41, 39, 43, 120, 38])
print(result)
```

You should see something like:

```text
[-0.394, -0.3275, -0.3607, -0.4272, -0.2943, 2.2641, -0.4604]
```

Most values sit near 0, but the 120-sales day gets a big z-score - it is several 'usual steps' above normal, worth investigating.

> **Watch out:** A common alert rule: anything beyond +2 or -2 gets a second look.

## Check yourself

1. A z-score of 0 means what?
2. Is a z-score of +2.8 or +0.4 more unusual?
3. Why are z-scores useful for comparing two different products?

<details>
<summary>Show answers</summary>

1. The value equals the average - completely typical.

2. +2.8. The further from 0, the more unusual the value.

3. They put both on the same surprise scale, even if one sells 10 units and the other sells 10,000.

</details>

## Try this now

Take your last 10 order quantities, run zscore, and list any day with a z-score beyond +2 or below -2.

---
[← Descriptive Stats](descriptive_stats.md) · [Back to Statistics & Accuracy library](README.md) · [Coefficient of Variation →](coefficient_of_variation.md)
