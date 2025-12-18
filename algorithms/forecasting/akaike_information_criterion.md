---
title: "AIC (Akaike Information Criterion) | supplycm Algorithm Library"
description: "Plain-English explanation of akaike_information_criterion from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, akaike_information_criterion, supply chain, plain english, forecasting"
---

# AIC (Akaike Information Criterion)

> **Call it:** `from supplycm.forecasting import akaike_information_criterion` · **Level:** Advanced · **You need:** basic arithmetic only

AIC scores models on a honest curve: fit quality minus a penalty for each parameter. Comparing two models? The LOWER AIC wins - it achieved its fit with less complexity. It is the referee that stops you from buying accuracy with overfitting.

**Think of it like this:** Judging two students' essays with a penalty per page: the shorter essay must be genuinely better to win - padding is taxed.

## When to reach for it

- Choosing between candidate models of different complexity
- Automated model selection across many SKUs

## Try it with supplycm

```python
from supplycm.forecasting import akaike_information_criterion

result = akaike_information_criterion(residuals=[0.5, -0.3, 0.4, -0.2, 0.1], k=3)
print(result)
```

You should see something like:

```text
-5.0364
```

One AIC number - meaningful only in comparison: recompute with the other model's residuals and parameter count, lower wins.

## Check yourself

1. What does AIC penalize?
2. AIC vs BIC - whose penalty is harsher?
3. Is an AIC of 42 'good'?

<details>
<summary>Show answers</summary>

1. Every extra parameter - complexity must pay rent in genuine fit improvement or the score rises.

2. BIC's - it taxes complexity harder and favors simpler models, especially with lots of data.

3. Meaningless alone - AIC only compares models on the SAME data; lower-than-the-alternative is the entire grammar.

</details>

## Try this now

Score a 2-parameter vs 5-parameter model with similar residuals; verify AIC crowns the simpler one unless fit truly improves.

---
[← Inverse Box-Cox Transform](inverse_box_cox.md) · [Back to Forecasting library](README.md) · [BIC (Bayesian Information Criterion) →](bayesian_information_criterion.md)
