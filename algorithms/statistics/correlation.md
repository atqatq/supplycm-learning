---
title: "Correlation | supplycm Algorithm Library"
description: "Plain-English explanation of correlation from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, correlation, supply chain, plain english, statistics & accuracy"
---

# Correlation

> **Call it:** `from supplycm.statistics import correlation` · **Level:** Beginner · **You need:** basic arithmetic only

Correlation measures how two things move together, from -1 to +1. +1 means perfect togetherness, 0 means no relationship, -1 means perfect opposites. Use it to find drivers of demand, like ice cream sales vs temperature, or to check whether two products rise and fall together.

**Think of it like this:** Dancing partners: +1 they mirror each other perfectly, 0 they ignore each other, -1 they do the exact opposite.

## When to reach for it

- Finding variables that could explain your demand (weather, price, promotions)
- Checking if two products' sales move together (useful for grouping and bundling)

## Try it with supplycm

```python
from supplycm.statistics import correlation

result = correlation([10, 20, 30, 40, 50], [12, 24, 31, 39, 52])
print(result)
```

You should see something like:

```text
0.9941
```

The correlation is very close to +1 - these two series rise and fall almost in lockstep.

## Check yourself

1. Correlation of -0.9 means what?
2. Does a strong correlation prove one causes the other?
3. Why should forecasters hunt for correlated drivers?

<details>
<summary>Show answers</summary>

1. The two move almost perfectly in opposite directions - when one goes up, the other goes down.

2. No. Both may be driven by a third factor (like season). Correlation is a clue, not proof.

3. If you can predict the driver (like temperature), you inherit predictive power for your demand.

</details>

## Try this now

Invent two series that would correlate around -1 (e.g., hot days vs hot-chocolate sales) and verify with the function.

---
[← Kurtosis](kurtosis.md) · [Back to Statistics & Accuracy library](README.md) · [Spearman Correlation →](spearman_correlation.md)

*New to this topic? Start with the core lesson first: [02_forecasting.md](../../modules/02_forecasting.md).*
