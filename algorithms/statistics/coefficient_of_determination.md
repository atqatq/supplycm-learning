---
title: "Coefficient of Determination | supplycm Algorithm Library"
description: "Plain-English explanation of coefficient_of_determination from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, coefficient_of_determination, supply chain, plain english, statistics & accuracy"
---

# Coefficient of Determination

> **Call it:** `from supplycm.statistics import coefficient_of_determination` · **Level:** Intermediate · **You need:** basic arithmetic only

This is R-squared's other name, computed between two series: it answers 'what fraction of the variation does one series explain about the other?'. Useful beyond straight-line models - any time you want to know how much of the pattern your numbers, plan, or model captured.

**Think of it like this:** Like asking what share of a movie's plot the trailer gave away - 0.9 means you saw nearly everything coming.

## When to reach for it

- Squaring a correlation to get an explained-share for any relationship
- Explaining to managers how much of demand a driver explains, in percent

## Try it with supplycm

```python
from supplycm.statistics import coefficient_of_determination

result = coefficient_of_determination([100, 200, 300, 400], [105, 195, 305, 395])
print(result)
```

You should see something like:

```text
0.998
```

Close to 1 - almost all of the movement in the first series is reflected in the second.

## Check yourself

1. If correlation is 0.5, what is the coefficient of determination?
2. Explain R-squared 0.25 in manager language.
3. What value would a perfect predictor have?

<details>
<summary>Show answers</summary>

1. 0.25 - you square it. Half the correlation becomes a quarter of the explanation.

2. Only about a quarter of the variation is explained; three quarters is unexplained noise or other factors.

3. 1 (100% of variation explained).

</details>

## Try this now

Compute correlation between two invented series, square it, and confirm it matches coefficient_of_determination.

---
[← R-Squared](r_squared.md) · [Back to Statistics & Accuracy library](README.md) · [Adjusted R-Squared →](adjusted_r_squared.md)
