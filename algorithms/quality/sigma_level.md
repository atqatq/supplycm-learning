---
title: "Sigma Level | supplycm Algorithm Library"
description: "Plain-English explanation of sigma_level from the supplycm Quality module, with a runnable Python example and self-check questions."
keywords: "supplycm, quality, sigma_level, supply chain, plain english, quality"
---

# Sigma Level

> **Call it:** `from supplycm.quality import sigma_level` · **Level:** Beginner · **You need:** basic arithmetic only

Sigma level converts DPMO into the famous Six Sigma scale. 6 sigma means about 3.4 defects per million chances; 3 sigma means about 67,000. The function does the conversion so you can say 'we are a 3.5 sigma process' and everyone knows what that costs.

**Think of it like this:** Exam grading bands: same score, but the grade (A/B/C) is what people quote and compare.

## When to reach for it

- Translating DPMO into the language executives know
- Setting improvement targets ('from 3.1 to 4.0 sigma this year')

## Try it with supplycm

```python
from supplycm.quality import sigma_level

result = sigma_level(6210)
print(result)
```

You should see something like:

```text
4.0
```

4.0 sigma - every step up of one sigma cuts defects dramatically, which is why the climb gets harder but pays more.

## Check yourself

1. Roughly how many DPMO is 6 sigma?
2. Is '3 sigma' good enough?
3. Which journey is harder: 2 to 3 sigma, or 5 to 6 sigma?

<details>
<summary>Show answers</summary>

1. 3.4 - near perfection.

2. About 66,800 DPMO - for a hospital pharmacy or an airline that would be a disaster; context decides.

3. 5 to 6 - each sigma step removes an order of magnitude more defects.

</details>

## Try this now

Convert 66,807 DPMO to sigma; then compute DPMO for 233 and for 3.4 and map all three onto the scale.

---
[← DPMO (Defects Per Million Opportunities)](dpmo.md) · [Back to Quality library](README.md) · [Process Capability (Cp) →](process_capability_cp.md)

*New to this topic? Start with the core lesson first: [07_quality.md](../../modules/07_quality.md).*
