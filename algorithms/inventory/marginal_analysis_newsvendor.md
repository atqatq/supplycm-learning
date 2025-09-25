---
title: "Marginal Analysis Newsvendor | supplycm Algorithm Library"
description: "Plain-English explanation of marginal_analysis_newsvendor from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, marginal_analysis_newsvendor, supply chain, plain english, inventory"
---

# Marginal Analysis Newsvendor

> **Call it:** `from supplycm.inventory import marginal_analysis_newsvendor` · **Level:** Intermediate · **You need:** basic arithmetic only

A data-driven cousin of the newsvendor: give it discrete demand scenarios with probabilities, and it adds one unit at a time only while the expected gain stays positive. It stops exactly where ordering one more would expect to lose money. No formulas to trust - just arithmetic you can watch.

**Think of it like this:** Adding chairs to a seminar: keep adding while the expected extra attendance pays for the chair; stop at the chair that would likely sit empty.

## When to reach for it

- Discrete scenarios from history (100 sold twice, 150 sold five times...)
- Teaching WHY optimal stock exceeds average demand

## Try it with supplycm

```python
from supplycm.inventory import marginal_analysis_newsvendor

result = marginal_analysis_newsvendor(unit_cost=3, selling_price=6, salvage_value=1, demand_scenarios=[(80, 0.1), (100, 0.2), (120, 0.4), (140, 0.2), (160, 0.1)])
print(result)
```

You should see something like:

```text
120
```

An optimal order quantity from the scenario table - notice it lands above the average demand, because missed sales hurt more than leftovers.

## Check yourself

1. Why does the answer exceed average demand?
2. Scenario probabilities are guesses. How sensitive is the answer?
3. Where do good scenarios come from?

<details>
<summary>Show answers</summary>

1. Asymmetric costs: an unsold unit loses a little (cost minus salvage); a missed sale loses the full margin - the balance tilts upward.

2. Moderately - shifting probability mass to high demand raises the optimum; run two scenario sets and compare.

3. History (sales by weather/price bucket), analog products, and structured judgment - never from one season alone.

</details>

## Try this now

Shift 20% probability from 120 to 160 in the example and verify the optimum climbs - explain the direction.

---
[← Newsvendor Model](newsvendor_model.md) · [Back to Inventory library](README.md) · [Optimal Stockout Probability →](optimal_stockout_probability.md)
