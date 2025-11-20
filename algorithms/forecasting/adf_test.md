---
title: "ADF Test Statistic (Stationarity) | supplycm Algorithm Library"
description: "Plain-English explanation of adf_test from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, adf_test, supply chain, plain english, forecasting"
---

# ADF Test Statistic (Stationarity)

> **Call it:** `from supplycm.forecasting import adf_test` · **Level:** Advanced · **You need:** basic arithmetic only

Many models assume the series is STATIONARY - same average behavior over time. The ADF statistic tests for a unit root, the mathematical signature of a wandering, trend-riding series. Very negative values say 'stationary, safe to model'; values near zero warn 'this series drifts'.

**Think of it like this:** Checking whether a river has a current: ADF is the floating leaf test - leaves that drift steadily downstream reveal the current (trend).

## When to reach for it

- Pre-flight checks before AR/MA/VAR modeling
- Explaining WHY you differenced a series before modeling

## Try it with supplycm

```python
from supplycm.forecasting import adf_test

result = adf_test([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
print(result)
```

You should see something like:

```text
-0.5477
```

A value near zero for this steadily climbing series - not stationary; difference the series or detrend before modeling.

## Check yourself

1. What is a 'unit root' in plain words?
2. Series fails ADF. Standard fix?
3. Why does stationarity matter to forecasters?

<details>
<summary>Show answers</summary>

1. The series' level wanders without a home - shocks accumulate forever instead of reverting.

2. Difference it (model the CHANGES) - most trending business series turn stationary after one difference.

3. Because models extrapolate patterns they assume are stable - non-stationary data breaks that promise.

</details>

## Try this now

Run ADF on a random-walk series vs a mean-reverting one; compare statistics and explain each verdict.

---
[← Ljung-Box Test Statistic](ljung_box_test.md) · [Back to Forecasting library](README.md) · [KPSS Test Statistic (Stationarity) →](kpss_test.md)
