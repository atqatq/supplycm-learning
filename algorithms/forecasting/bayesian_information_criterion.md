---
title: "BIC (Bayesian Information Criterion) | supplycm Algorithm Library"
description: "Plain-English explanation of bayesian_information_criterion from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, bayesian_information_criterion, supply chain, plain english, forecasting"
---

# BIC (Bayesian Information Criterion)

> **Call it:** `from supplycm.forecasting import bayesian_information_criterion` · **Level:** Advanced · **You need:** basic arithmetic only

AIC's stricter sibling: same idea - fit minus complexity penalty - but the penalty grows with sample size. With lots of data, BIC pushes HARD toward simple models. When AIC and BIC disagree, you've found the complexity debate worth having.

**Think of it like this:** A gym trainer who gets stricter as you gain experience: early on, extra exercises help; later, every unnecessary one is called out.

## When to reach for it

- Model selection with large samples where parsimony matters
- Second opinions when AIC alone feels too permissive

## Try it with supplycm

```python
from supplycm.forecasting import bayesian_information_criterion

result = bayesian_information_criterion(residuals=[0.5, -0.3, 0.4, -0.2, 0.1], k=3)
print(result)
```

You should see something like:

```text
-6.2081
```

A BIC number - bigger than AIC's here (harsher penalty); compare both across candidate models and note any disagreement.

## Check yourself

1. When do AIC and BIC pick different winners?
2. Which should guide SKU-level automated selection?
3. What does BIC's data-growing penalty imply?

<details>
<summary>Show answers</summary>

1. When a complex model fits somewhat better - AIC may accept it, BIC may reject the complexity as not worth it at that sample size.

2. BIC for stability and simplicity; AIC when small fit gains matter operationally.

3. As evidence accumulates, only genuinely useful complexity survives - big data makes the bar higher, not lower.

</details>

## Try this now

Score three nested models with AIC and BIC; find the sample size where their verdicts split and explain why.

---
[← AIC (Akaike Information Criterion)](akaike_information_criterion.md) · [Back to Forecasting library](README.md) · [Bates-Granger Forecast Combination →](bates_granger_combination.md)
