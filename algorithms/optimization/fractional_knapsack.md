---
title: "Fractional Knapsack | supplycm Algorithm Library"
description: "Plain-English explanation of fractional_knapsack from the supplycm Optimization module, with a runnable Python example and self-check questions."
keywords: "supplycm, optimization, fractional_knapsack, supply chain, plain english, optimization"
---

# Fractional Knapsack

> **Call it:** `from supplycm.optimization import fractional_knapsack` · **Level:** Beginner · **You need:** basic arithmetic only

Fill a limited capacity with the best value: take items by value density (value per kilo), best first, and allow FRACTIONS of the last item that doesn't quite fit. Greedy is provably optimal here - the friendliest knapsack variant.

**Think of it like this:** Loading a delivery van with flour sold by weight: load the highest value-per-kilo goods first, and the last sack can be a partial one.

## When to reach for it

- Divisible goods (liquids, grain, budget allocation)
- Any resource split where 'take 62% of it' is legal

## Try it with supplycm

```python
from supplycm.optimization import fractional_knapsack

result = fractional_knapsack(weights=[10, 20, 30], values=[60, 100, 120], capacity=50)
print(result)
```

You should see something like:

```text
[240.0, [1.0, 1.0, 0.6667]]
```

Total value 240 with fractions [1.0, 1.0, 0.67] - the last item contributed only what fit; greedy by density was provably right.

## Check yourself

1. Why is greedy optimal HERE but not for the 0-1 knapsack?
2. What's 'value density'?
3. Where does this model appear in supply chains?

<details>
<summary>Show answers</summary>

1. Fractions erase the awkwardness - leftover space can always be filled with a partial item, so density ordering never misleads.

2. Value divided by weight - the worth of each kilo; loading by density is the whole algorithm.

3. Budget allocation across divisible investments, cargo mixing, and media buying - anywhere partial takes are legal.

</details>

## Try this now

Recompute with all values doubled - does the SELECTION change? Why does density, not total value, decide?

---
[← Quick Sort](quick_sort.md) · [Back to Optimization library](README.md) · [0-1 Knapsack (Dynamic Programming) →](knapsack_01_dp.md)
