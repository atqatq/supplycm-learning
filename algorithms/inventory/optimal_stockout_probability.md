---
title: "Optimal Stockout Probability | supplycm Algorithm Library"
description: "Plain-English explanation of optimal_stockout_probability from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, optimal_stockout_probability, supply chain, plain english, inventory"
---

# Optimal Stockout Probability

> **Call it:** `from supplycm.inventory import optimal_stockout_probability` · **Level:** Advanced · **You need:** basic arithmetic only

Economics in reverse: instead of picking service level then computing stock, this computes the stockout PROBABILITY that maximizes profit, straight from the cost ratios. High margins imply low tolerated stockout chances; commodity margins tolerate frequent misses. It is the newsvendor's answer expressed as a probability.

**Think of it like this:** A farmer deciding what share of market days to risk showing up with empty crates - the tolerable miss rate falls out of the price of crops vs seeds.

## When to reach for it

- Setting service level targets from economics, not habit
- Challenging arbitrary 'we target 99%' policies

## Try it with supplycm

```python
from supplycm.inventory import optimal_stockout_probability

result = optimal_stockout_probability(unit_cost=3, selling_price=6, salvage_value=1, shortage_cost=0)
print(result)
```

You should see something like:

```text
0.4
```

A tolerable stockout probability around a third - thin margins can afford frequent small misses; raise the margin and watch the tolerated risk collapse.

## Check yourself

1. Why can tolerating MORE stockouts be optimal?
2. Margin doubles. What happens to the tolerated stockout probability?
3. How do you convert this probability into stock?

<details>
<summary>Show answers</summary>

1. Protection isn't free - if missed sales cost little, insuring against every one wastes more than it saves.

2. It drops sharply - richer margins make every missed sale more expensive to risk.

3. Pick the inventory (via safety stock or newsvendor) whose demand coverage matches the tolerated miss rate.

</details>

## Try this now

Compute tolerated stockout probability for margin 2 vs 20 on the same cost base - and translate both into service promises.

---
[← Marginal Analysis Newsvendor](marginal_analysis_newsvendor.md) · [Back to Inventory library](README.md) · [Perishable Inventory Order →](perishable_inventory.md)
