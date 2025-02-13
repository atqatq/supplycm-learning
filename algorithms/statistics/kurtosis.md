---
title: "Kurtosis | supplycm Algorithm Library"
description: "Plain-English explanation of kurtosis from the supplycm Statistics & Accuracy module, with a runnable Python example and self-check questions."
keywords: "supplycm, statistics, kurtosis, supply chain, plain english, statistics & accuracy"
---

# Kurtosis

> **Call it:** `from supplycm.statistics import kurtosis` · **Level:** Advanced · **You need:** basic arithmetic only

Kurtosis measures how often extreme values show up. High kurtosis means your data is mostly calm but occasionally explodes - rare, sharp shocks. Low kurtosis means values are spread fairly evenly with few surprises. In supply chains, high kurtosis is the signature of disruption-prone demand.

**Think of it like this:** A calm lake that occasionally has a huge wave - versus a choppy sea with uniform small waves.

## When to reach for it

- Assessing whether a product's history contains shock events worth modeling separately
- Risk reviews: spotting items whose demand looks quiet but can spike violently

## Try it with supplycm

```python
from supplycm.statistics import kurtosis

result = kurtosis([100, 101, 99, 100, 102, 98, 100, 300])
print(result)
```

You should see something like:

```text
3.1396
```

High kurtosis - most days are tame around 100, but that 300 is exactly the kind of rare shock kurtosis is built to detect.

## Check yourself

1. High kurtosis means what kind of extremes?
2. Is kurtosis about the direction of the tail (left/right)?
3. Why should a risk manager love kurtosis?

<details>
<summary>Show answers</summary>

1. Rare but sharp ones - long stretches of calm punctuated by big spikes.

2. No - that is skewness. Kurtosis is about how heavy the tails are in general.

3. It reveals products that look stable on average but hide shock risk in the tails.

</details>

## Try this now

Compare kurtosis of [10,12,11,10,13,11] vs [10,10,10,10,10,60] and explain the difference in plain words.

---
[← Skewness](skewness.md) · [Back to Statistics & Accuracy library](README.md) · [Correlation →](correlation.md)
