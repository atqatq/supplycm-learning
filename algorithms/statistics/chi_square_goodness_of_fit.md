---
title: "Chi-Square Goodness of Fit | supplycm Algorithm Library"
description: "Plain-English explanation of chi_square_goodness_of_fit from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, chi_square_goodness_of_fit, supply chain, plain english, statistics & accuracy"
---

# Chi-Square Goodness of Fit

> **Call it:** `from supplycm.statistics import chi_square_goodness_of_fit` · **Level:** Intermediate · **You need:** basic arithmetic only

Compares observed counts against expected counts across categories. A small statistic means reality matches your expectation; a big one means some category is off. Perfect for discrete questions: are weekdays equally busy? Do defects cluster on one line?

**Think of it like this:** A casino inspector checking whether a dice really rolls each number a sixth of the time.

## When to reach for it

- Testing if weekday demand shares match your planning assumptions
- Checking whether defects are spread evenly or concentrate somewhere

## Try it with supplycm

```python
from supplycm.statistics import chi_square_goodness_of_fit

result = chi_square_goodness_of_fit([90, 85, 95, 88, 92], [90, 90, 90, 90, 90])
print(result)
```

You should see something like:

```text
0.6444
```

A small statistic relative to the counts - the observed weekday pattern is close to what you expected; no alarm.

## Check yourself

1. What do 'observed' and 'expected' mean here?
2. Does chi-square care about the size of counts?
3. Saturday demand keeps beating the plan. Which test flags it?

<details>
<summary>Show answers</summary>

1. Observed = what actually happened; expected = what your assumption predicts should happen.

2. Yes - it works on counts, so you need enough volume per category for the test to mean anything.

3. Chi-square across weekdays would show one category contributing a big chunk of the statistic.

</details>

## Try this now

Compare your imagined weekday sales to an even-spread assumption and name the day that drives the statistic.

---
[← Jarque-Bera Statistic](jarque_bera_test.md) · [Back to Statistics & Accuracy library](README.md) · [Kolmogorov-Smirnov Test (One Sample) →](kolmogorov_smirnov_test.md)
