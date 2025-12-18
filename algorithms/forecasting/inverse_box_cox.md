---
title: "Inverse Box-Cox Transform | supplycm Algorithm Library"
description: "Plain-English explanation of inverse_box_cox from the supplycm Forecasting module, with a runnable Python example and self-check questions."
keywords: "supplycm, forecasting, inverse_box_cox, supply chain, plain english, forecasting"
---

# Inverse Box-Cox Transform

> **Call it:** `from supplycm.forecasting import inverse_box_cox` · **Level:** Advanced · **You need:** basic arithmetic only

The way home: after modeling on the transformed scale, this restores forecasts to real units. Skip it and your plans quote 'log-demand' numbers nobody can order against. Every Box-Cox journey needs this return ticket.

**Think of it like this:** Landing the airplane after flying on instruments - the flight was smoother up there, but passengers live on the ground.

## When to reach for it

- Converting transformed forecasts back to orderable units
- Closing the loop in any Box-Cox workflow

## Try it with supplycm

```python
from supplycm.forecasting import inverse_box_cox

result = inverse_box_cox([4.6, 4.7, 4.8], lam=0.0)
print(result)
```

You should see something like:

```text
[99.4843, 109.9472, 121.5104]
```

Real-unit forecasts return - exponential growth reappears in the numbers, ready for actual order quantities.

## Check yourself

1. What happens if you forget the inverse step?
2. Why must lambda match between transform and inverse?
3. Where do prediction INTERVALS get transformed?

<details>
<summary>Show answers</summary>

1. You plan with log-scale numbers - quantities 100x too small or meaningless - a classic, costly pipeline bug.

2. They are one operation in two directions - mismatched lambda lands you in the wrong units entirely.

3. Through the same inverse - intervals that were symmetric up there come back asymmetric down here, honestly.

</details>

## Try this now

Round-trip a series: transform with lambda 0, verify the inverse returns the originals exactly - then break lambda and observe.

---
[← Box-Cox Transform](box_cox_transform.md) · [Back to Forecasting library](README.md) · [AIC (Akaike Information Criterion) →](akaike_information_criterion.md)
