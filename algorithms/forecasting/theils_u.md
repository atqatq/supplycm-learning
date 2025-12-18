---
title: "Theil's U | supplycm Algorithm Library"
description: "Plain-English explanation of theils_u from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, theils_u, supply chain, plain english, forecasting"
---

# Theil's U

> **Call it:** `from supplycm.forecasting import theils_u` · **Level:** Intermediate · **You need:** basic arithmetic only

A fairness ratio: your forecast's error divided by the naive forecast's error. Below 1.0, you beat copying yesterday; above 1.0, you're losing to laziness. U near 0.8 reads '20% better than the benchmark' - instant context for any error metric.

**Think of it like this:** A race against the house champion: the time ratio - not your raw time - tells whether you actually deserve the trophy.

## When to reach for it

- Adding instant context to raw error numbers
- Vetting vendor forecasts that quote impressive-sounding MAPEs

## Try it with supplycm

```python
from supplycm.forecasting import theils_u

result = theils_u(actual=[100, 120, 130, 150], forecast=[105, 115, 138, 145])
print(result)
```

You should see something like:

```text
0.0467
```

Well below 1.0 - this forecast genuinely outperforms the naive benchmark; the effort behind it is paying rent.

## Check yourself

1. U = 1.1 - verdict?
2. Why compare against naive specifically?
3. Can a great MAPE hide a bad U?

<details>
<summary>Show answers</summary>

1. 11% worse than naive - drop the method or fix it; copying yesterday was better.

2. It is the zero-effort benchmark everyone understands - beating it is the minimum bar for any 'smart' method.

3. Yes - on easy-to-forecast series, naive also has great MAPE; U reveals whether YOUR method added anything.

</details>

## Try this now

Compute U for two candidate forecasts on the same series; reject any that doesn't clear 1.0 and justify to the team.

---
[← Hurst Exponent](hurst_exponent.md) · [Back to Forecasting library](README.md) · [Box-Cox Transform →](box_cox_transform.md)
