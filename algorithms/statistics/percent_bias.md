---
title: "Percent Bias (PBIAS) | supplycm Algorithm Library"
description: "Plain-English explanation of percent_bias from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, percent_bias, supply chain, plain english, statistics & accuracy"
---

# Percent Bias (PBIAS)

> **Call it:** `from supplycm.statistics import percent_bias` · **Level:** Intermediate · **You need:** basic arithmetic only

PBIAS sums ALL errors and divides by the sum of all actuals, giving one overall percentage tilt. Unlike MAPE, it treats every unit equally regardless of day size, so big sales days count big - which matches how money actually flows.

**Think of it like this:** Weighing the year's total shortfall against the year's total sales, instead of averaging daily percentages.

## When to reach for it

- Executive reporting: one clean percent-of-total bias number
- Volume-weighted accuracy checks where big days matter most

## Try it with supplycm

```python
from supplycm.statistics import percent_bias

result = percent_bias([500, 20, 300], [450, 30, 330])
print(result)
```

You should see something like:

```text
-1.2195
```

A small positive bias overall - the misses on the big days dominate, exactly how a P&L would feel them.

## Check yourself

1. How does PBIAS differ from MAPE?
2. Which is closer to financial impact?
3. PBIAS = -5% on annual demand of 1M units means what?

<details>
<summary>Show answers</summary>

1. MAPE averages per-day percentages (each day counts equally); PBIAS weights by volume (big days count more).

2. PBIAS - money scales with units, and PBIAS weights units.

3. You planned about 50,000 units of phantom demand - real money tied up in stock.

</details>

## Try this now

For a 5-week history, compute MAPE and PBIAS; identify a case where they disagree and explain why.

---
[← MPE (Mean Percentage Error)](mean_percentage_error.md) · [Back to Statistics & Accuracy library](README.md) · [MASE (Mean Absolute Scaled Error) →](mase.md)
