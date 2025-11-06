---
title: "TSB Method | supplycm Algorithm Library"
description: "Plain-English explanation of tsb_method from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, tsb_method, supply chain, plain english, forecasting"
---

# TSB Method

> **Call it:** `from supplycm.forecasting import tsb_method` · **Level:** Advanced · **You need:** basic arithmetic only

TSB (Teunter-Syntetos-Babai) fixes Croston's blind spot for DEMAND LOSS: it tracks the probability that a period has ANY sale, and the size when it does. When products fade in and out, TSB's probability engine notices what Croston ignores - zeros carry information.

**Think of it like this:** Tracking both how often a phone rings AND the chance it ever rings again - silence updates the second number.

## When to reach for it

- Intermittent demand with true demand loss (obsolete, churn)
- Modern spare-parts planning where obsolescence is real

## Try it with supplycm

```python
from supplycm.forecasting import tsb_method

result = tsb_method([2, 0, 0, 5, 0, 3, 0, 0, 0, 0], alpha=0.2, beta=0.2)
print(result)
```

You should see something like:

```text
[0.08, 0.064, 0.0512, 0.3992, 0.3193, 0.6517, 0.5214, 0.4171, 0.3337, 0.2669]
```

Per-period expected demand returns - after the trailing zeros, the probability component sags and the expectation follows: TSB reads silence as signal.

## Check yourself

1. What does TSB track that Croston doesn't?
2. When does TSB beat SBA?
3. What do alpha and beta mean here?

<details>
<summary>Show answers</summary>

1. The PROBABILITY of demand occurring each period - intervals become probabilities, and silence moves them.

2. When demand genuinely disappears or returns - SBA assumes intervals are stable; TSB lets the demand rate itself shift.

3. Alpha updates the demand probability on each period's outcome; beta updates the size estimate when demand happens.

</details>

## Try this now

Feed TSB a series that goes silent at period 6 and stays silent; watch the expectation decay - compare with SBA's behavior.

---
[← SBA (Syntetos-Boylan Approximation)](sba_method.md) · [Back to Forecasting library](README.md) · [Pegels Classification →](pegels_classification.md)
