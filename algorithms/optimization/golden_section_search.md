---
title: "Golden Section Search | supplycm Algorithm Library"
description: "Plain-English explanation of golden_section_search from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, golden_section_search, supply chain, plain english, optimization"
---

# Golden Section Search

> **Call it:** `from supplycm.optimization import golden_section_search` · **Level:** Intermediate · **You need:** basic arithmetic only

Finding the lowest point of a curve WITHOUT derivatives: probe two interior points of a range, keep the side holding the minimum, shrink, repeat. The golden ratio spacing lets each step reuse one probe - elegant, derivative-free, unfailingly convergent on unimodal curves.

**Think of it like this:** Tuning a radio without a signal meter: test two dial positions, keep the clearer half of the band, and narrow in - your ear needs no mathematics of the slope.

## When to reach for it

- Tuning one continuous parameter (order quantity, price point)
- Any single-variable search where derivatives are unavailable

## Try it with supplycm

```python
from supplycm.optimization import golden_section_search

result = golden_section_search(f=lambda x: (x - 3) ** 2, a=0, b=10)
print(result)
```

You should see something like:

```text
3.0
```

The minimum near 3.0 - each step discarded a whole side of the range; the golden ratio kept one probe per iteration.

## Check yourself

1. Why 'golden section'?
2. What must the function satisfy?
3. Derivative methods vs this - when choose it?

<details>
<summary>Show answers</summary>

1. Probe spacing uses the golden ratio so each iteration reuses one interior point - one new evaluation per step, not two.

2. Unimodality on the range - one valley only; multiple dips can strand the search in the wrong one.

3. When derivatives are unavailable, noisy, or fiddly - golden section asks only 'which probe is lower?'

</details>

## Try this now

Minimize a function on [0, 5] by hand with four probes; compare your bracket with the function's path.

---
[← Branch and Bound](branch_and_bound.md) · [Back to Optimization library](README.md) · [Gradient Descent →](gradient_descent.md)
