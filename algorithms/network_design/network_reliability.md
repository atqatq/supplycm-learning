---
title: "Network Reliability | supplycm Algorithm Library"
description: "Plain-English explanation of network_reliability from the supplycm Network Design module, with a runnable Python example and self-check questions."
keywords: "supplycm, network_design, network_reliability, supply chain, plain english, network design"
---

# Network Reliability

> **Call it:** `from supplycm.network_design import network_reliability` · **Level:** Advanced · **You need:** basic arithmetic only

Each node works with some probability - what's the chance the NETWORK still functions? This combines component reliabilities and backup edges into one survival probability. It turns 'we have redundancy' from a feeling into a number.

**Think of it like this:** A bridge with pillars each 95% reliable: the question isn't each pillar - it's whether the bridge as a whole stands on your worst day.

## When to reach for it

- Scoring network designs on survival, not just cost
- Comparing a hub-and-spoke design against a meshed one

## Try it with supplycm

```python
from supplycm.network_design import network_reliability

result = network_reliability(node_reliabilities={0: 0.95, 1: 0.9, 2: 0.85}, edges=[(0, 1, 0.9), (1, 2, 0.8), (0, 2, 0.7)])
print(result)
```

You should see something like:

```text
0.7268
```

One survival probability - add the backup edge (0,2) and re-run to price exactly what redundancy bought you.

## Check yourself

1. Why isn't network reliability just the average of node reliabilities?
2. What does a redundant edge really buy?
3. How would you present this to a board?

<details>
<summary>Show answers</summary>

1. Because paths combine in parallel AND series - structure, not averaging, decides survival.

2. A second chance: the connection survives if EITHER route works - probabilities combine multiplicatively in your favor.

3. As expected disruption cost: survival probability times outage impact - suddenly the backup edge has a payback.

</details>

## Try this now

Compute reliability with and without the backup edge; multiply the difference by an outage cost and defend the investment.

---
[← Facility Location (Fixed Cost)](facility_location_fixed_cost.md) · [Back to Network Design library](README.md) · [Single-Source Allocation →](single_source_allocation.md)
