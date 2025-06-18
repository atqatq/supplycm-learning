---
title: "Monte Carlo Risk Simulation | supplycm Algorithm Library"
description: "Plain-English explanation of monte_carlo_risk from the supplycm Simulation module, with a runnable Python example and self-check questions."
keywords: "supplycm, simulation, monte_carlo_risk, supply chain, plain english, simulation"
---

# Monte Carlo Risk Simulation

> **Call it:** `from supplycm.simulation import monte_carlo_risk` · **Level:** Intermediate · **You need:** basic arithmetic only

Define scenarios (best case, likely case, disaster) with probabilities, then let the computer replay your plan thousands of times. You get the full distribution of outcomes - including the tail scenarios that averages hide. Risk planning becomes arithmetic plus repetition.

**Think of it like this:** Stress-testing a bridge with thousands of virtual trucks and storms before opening it to real traffic.

## When to reach for it

- Quantifying exposure to supplier failure, price spikes, or demand collapse
- Deciding how much buffer (stock, cash, backup capacity) is enough

## Try it with supplycm

```python
from supplycm.simulation import monte_carlo_risk

result = monte_carlo_risk(scenarios=[{'cost_mean': 50000, 'cost_std': 5000, 'probability': 0.7}, {'cost_mean': 55000, 'cost_std': 6000, 'probability': 0.25}, {'cost_mean': 90000, 'cost_std': 12000, 'probability': 0.05}], n_simulations=10000)
print(result)
```

You should see something like:

```text
{'expected_cost': 53296.0639, 'percentile_5': 0, 'percentile_95': 118069.5813, 'var_95': 118069.5813}
```

The summary shows how often each scenario family hit and the spread of total cost - the 5% disaster case is visible instead of hidden inside an average.

## Check yourself

1. Why not just multiply probabilities by outcomes?
2. What is a 'tail' outcome and why care?
3. How would you test a dual-sourcing plan here?

<details>
<summary>Show answers</summary>

1. Expected values hide the spread. Two plans can share an average while one occasionally ruins you - simulation reveals that.

2. The rare extreme results - they cause stockouts, missed payments, and lost customers, even if the average looks fine.

3. Give the backup supplier a scenario path (delayed, partial) and compare the simulated tail before vs after adding it.

</details>

## Try this now

Model a single-sourced part with a 5% failure scenario; run the sim, then add a backup source path and compare the tails.

---
[← Monte Carlo Inventory Simulation](monte_carlo_inventory.md) · [Back to Simulation library](README.md)

*New to this topic? Start with the core lesson first: [03_inventory.md](../../modules/03_inventory.md).*
