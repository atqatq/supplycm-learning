---
title: "MSE (Mean Squared Error) | supplycm Algorithm Library"
description: "Plain-English explanation of mse from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, mse, supply chain, plain english, statistics & accuracy"
---

# MSE (Mean Squared Error)

> **Call it:** `from supplycm.statistics import mse` · **Level:** Intermediate · **You need:** basic arithmetic only

MSE squares each error before averaging, which punishes big misses much harder than small ones. A day off by 20 hurts 4x more than a day off by 10. Use it when large errors are disproportionately costly - like stockouts on your best seller.

**Think of it like this:** Darts scoring where the outer rings cost exponentially more: one terrible throw can ruin the whole game.

## When to reach for it

- Comparing methods where occasional huge misses are unacceptable
- Tuning models that should prioritize avoiding disasters

## Try it with supplycm

```python
from supplycm.statistics import mse

result = mse([100, 100, 100, 100], [105, 95, 102, 160])
print(result)
```

You should see something like:

```text
913.5
```

Most errors are single digits, but the 60-unit miss dominates the total - MSE is shouting about that one bad day.

## Check yourself

1. Why does one huge error dominate MSE?
2. MSE vs MAE: which to use for a stable, low-stakes product?
3. What is RMSE's relationship to MSE?

<details>
<summary>Show answers</summary>

1. Squaring turns a 60 miss into 3,600 while a 5 miss is only 25 - the big miss outweighs dozens of small ones.

2. MAE - it reflects typical error without over-dramatizing rare spikes.

3. RMSE is the square root of MSE, bringing the error back into the original units.

</details>

## Try this now

For errors [5, 5, 5, 30] compute MAE and MSE; show how much the one big error changes each.

---
[← MAE (Mean Absolute Error)](mae.md) · [Back to Statistics & Accuracy library](README.md) · [RMSE (Root Mean Squared Error) →](rmse.md)
