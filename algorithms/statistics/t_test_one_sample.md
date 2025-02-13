---
title: "One-Sample T-Statistic | supplycm Algorithm Library"
description: "Plain-English explanation of t_test_one_sample from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, t_test_one_sample, supply chain, plain english, statistics & accuracy"
---

# One-Sample T-Statistic

> **Call it:** `from supplycm.statistics import t_test_one_sample` · **Level:** Intermediate · **You need:** basic arithmetic only

This tests whether your sample's average differs from a claimed value. It returns a t-statistic: values near 0 mean 'the data agrees with the claim'; large values (positive or negative) mean 'the data says otherwise'. For example: is the true lead time really the promised 10 days?

**Think of it like this:** A scale calibration check: weigh a known 1 kg weight many times - does the average reading actually sit at 1 kg?

## When to reach for it

- Auditing a supplier's claimed lead time against your recorded receipts
- Testing whether average demand has shifted from a historical level

## Try it with supplycm

```python
from supplycm.statistics import t_test_one_sample

result = t_test_one_sample([12, 11, 13, 12, 14, 11], mu0=10)
print(result)
```

You should see something like:

```text
4.5398
```

The t-statistic is clearly positive and large-ish: recorded lead times average well above the promised 10 days - raise it with the supplier.

## Check yourself

1. t near 0 means what?
2. Does a bigger sample make the same gap produce a bigger t?
3. You promised customers 5-day delivery; sampled actuals give t = +6. Action?

<details>
<summary>Show answers</summary>

1. The sample average sits close to the claimed value.

2. Yes - more data makes the same difference more statistically convincing.

3. The real average is far above 5 - fix the promise or fix the process.

</details>

## Try this now

You claim daily picks average 100 lines. Test it with a sample of 10 days you invent, and interpret t.

---
[← F-Test for Variances](f_test_variance.md) · [Back to Statistics & Accuracy library](README.md) · [Two-Sample T-Statistic →](t_test_two_sample.md)
