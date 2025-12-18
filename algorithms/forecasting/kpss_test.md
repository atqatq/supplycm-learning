---
title: "KPSS Test Statistic (Stationarity) | supplycm Algorithm Library"
description: "Plain-English explanation of kpss_test from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, kpss_test, supply chain, plain english, forecasting"
---

# KPSS Test Statistic (Stationarity)

> **Call it:** `from supplycm.forecasting import kpss_test` · **Level:** Advanced · **You need:** basic arithmetic only

The ADF's mirror image: KPSS assumes stationarity and looks for evidence AGAINST it. Using both gives balanced verdicts - ADF says 'no unit root found', KPSS says 'no stationarity violation found', and agreement between them is real confidence.

**Think of it like this:** Two judges, one presumed innocent and one presumed guilty: agreement on the verdict finally settles the case.

## When to reach for it

- Cross-checking ADF conclusions before modeling
- Teaching why single tests mislead

## Try it with supplycm

```python
from supplycm.forecasting import kpss_test

result = kpss_test([10, 10.5, 10.2, 10.4, 10.1, 10.3, 10.2, 10.4])
print(result)
```

You should see something like:

```text
0.1826
```

A small statistic for this well-behaved series - no evidence against stationarity; modeling may proceed.

## Check yourself

1. How do ADF and KPSS hypotheses differ?
2. Both tests agree the series is non-stationary. Action?
3. They disagree. Now what?

<details>
<summary>Show answers</summary>

1. Opposite nulls: ADF assumes non-stationarity (reject = stationary); KPSS assumes stationarity (reject = non-stationary).

2. Difference or detrend, then re-test - agreement makes the diagnosis credible.

3. Suspicion of borderline behavior - try both specifications, or use methods tolerant of mild non-stationarity.

</details>

## Try this now

Run ADF and KPSS on the same trending series and on a noisy stable one; fill a 2x2 verdict table.

---
[← ADF Test Statistic (Stationarity)](adf_test.md) · [Back to Forecasting library](README.md) · [Hurst Exponent →](hurst_exponent.md)
