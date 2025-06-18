---
title: "Monte Carlo Inventory Simulation | supplycm Algorithm Library"
description: "Plain-English explanation of monte_carlo_inventory from the supplycm Simulation module, with a runnable Python example and self-check questions."
keywords: "supplycm, simulation, monte_carlo_inventory, supply chain, plain english, simulation"
---

# Monte Carlo Inventory Simulation

> **Call it:** `from supplycm.simulation import monte_carlo_inventory` · **Level:** Intermediate · **You need:** basic arithmetic only

Instead of one tidy formula, this runs thousands of imaginary years of demand and lead times (with a fixed seed so you can reproduce results) and counts what happened: how often stock ran out, how much inventory sat around on average. It shows the RANGE of outcomes, not just the average.

**Think of it like this:** Rehearsing a product launch 10,000 times in a simulator to see every way it can go wrong - before it happens for real.

## When to reach for it

- Demand or lead times too weird for textbook safety-stock formulas
- Answering 'what service level does THIS policy actually deliver?'

## Try it with supplycm

```python
from supplycm.simulation import monte_carlo_inventory

result = monte_carlo_inventory(demand_mean=100, demand_std=20, order_quantity=600, lead_time=5, n_simulations=10000)
print(result)
```

You should see something like:

```text
{'stockout_probability': 0.0123, 'avg_shortage': 0.202, 'service_level': 0.9877}
```

The result dictionary summarizes thousands of simulated cycles - average stock, stockout frequency, and the honest spread of outcomes your policy produces.

> **Watch out:** Change one input at a time and compare runs - that is how simulation teaches you which lever matters.

## Check yourself

1. Why simulate instead of using a safety-stock formula?
2. What does the seed control?
3. Stockouts happen in 4% of simulated cycles. Options?

<details>
<summary>Show answers</summary>

1. Formulas lean on tidy assumptions (normal demand, fixed lead time). Simulation plays out reality, warts and all.

2. The randomness - same seed, same results. Change it and you see a different but statistically similar batch of futures.

3. Raise the reorder point, raise the order quantity, cut lead time, or accept it if the cost is small.

</details>

## Try this now

Run it with lead time 5 vs 10 and the same policy; explain in two sentences how lead time changes risk.

---
[Back to Simulation library](README.md) · [Monte Carlo Risk Simulation →](monte_carlo_risk.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
