---
title: "Bates-Granger Forecast Combination | supplycm Algorithm Library"
description: "Plain-English explanation of bates_granger_combination from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, bates_granger_combination, supply chain, plain english, forecasting"
---

# Bates-Granger Forecast Combination

> **Call it:** `from supplycm.forecasting import bates_granger_combination` · **Level:** Advanced · **You need:** basic arithmetic only

Two forecasts, each wrong differently - averaging them (weighted by inverse error) often beats either one. This computes the optimally weighted combination from their errors. Diversity is free accuracy: the ensemble principle, in its simplest business form.

**Think of it like this:** Two weather apps, one too optimistic, one too pessimistic - a smart blend outpredicts both, every time, on average.

## When to reach for it

- Combining statistical and judgmental forecasts
- Squeezing accuracy from models that disagree productively

## Try it with supplycm

```python
from supplycm.forecasting import bates_granger_combination

result = bates_granger_combination(forecasts=[[100, 105, 110], [110, 103, 112]], actuals=[102, 104, 111])
print(result)
```

You should see something like:

```text
[100.8333, 104.8333, 110.1667]
```

Combined forecasts per period - each series weighted by how well it predicted the actuals, so the better model gets the louder voice.

## Check yourself

1. Why does combining beat picking one winner?
2. When does combining FAIL to help?
3. How is this different from just averaging 50/50?

<details>
<summary>Show answers</summary>

1. Errors that don't overlap cancel - the blend's mistakes are smaller than either ingredient's.

2. When forecasts are near-identical - no diversity, no cancellation, just the same error twice.

3. Weights adapt to demonstrated accuracy - the reliable model speaks louder; 50/50 trusts blindly.

</details>

## Try this now

Combine an SES forecast with a Holt forecast on trending data; verify the blend's MAE beats both parents.

---
[← BIC (Bayesian Information Criterion)](bayesian_information_criterion.md) · [Back to Forecasting library](README.md) · [Top-Down Reconciliation →](top_down_reconciliation.md)
