---
title: "Wagner-Whitin (Optimal Lot Sizing) | supplycm Algorithm Library"
description: "Plain-English explanation of wagner_whitin from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, wagner_whitin, supply chain, plain english, inventory"
---

# Wagner-Whitin (Optimal Lot Sizing)

> **Call it:** `from supplycm.inventory import wagner_whitin` · **Level:** Advanced · **You need:** basic arithmetic only

The exact solution to dynamic lot sizing: a dynamic program that guarantees the minimum total setup-plus-holding cost over the horizon. It explores every sensible ordering plan implicitly and returns the best one. Slower and harder to explain - but it is the benchmark the heuristics chase.

**Think of it like this:** A chess engine versus good human rules: the heuristics play strong moves instantly; the engine proves the best line - use the engine when the game matters.

## When to reach for it

- High-stakes lot sizing where a few percent justify rigor
- Benchmarking which heuristic your data actually needs

## Try it with supplycm

```python
from supplycm.inventory import wagner_whitin

result = wagner_whitin(demands=[10, 20, 30, 40], setup_cost=100, holding_cost=1)
print(result)
```

You should see something like:

```text
[[0, 2], 260.0]
```

The optimal order periods and the optimal total cost - compare with your favorite heuristic and note the gap (often small, sometimes not).

## Check yourself

1. What does 'optimal' actually guarantee here?
2. Why don't all ERPs just run Wagner-Whitin?
3. What breaks the optimality promise in practice?

<details>
<summary>Show answers</summary>

1. Minimum setup-plus-holding cost for THIS demand series, horizon, and costs - nothing more (garbage inputs stay garbage).

2. Cost, computation across thousands of SKUs, and explainability - near-optimal heuristics are usually 'good enough' and far clearer.

3. Changing forecasts inside the horizon - the optimal plan assumed those demands; replanning erodes the guarantee.

</details>

## Try this now

Run Wagner-Whitin and Silver-Meal on [40, 5, 5, 40, 5, 5] with setup 90, holding 2 - find the gap and explain it.

---
[← Periodic Order Quantity (POQ)](periodic_order_quantity.md) · [Back to Inventory library](README.md) · [Fixed Order Quantity Lot Sizing →](fixed_order_quantity.md)
