---
title: "Min-Cost Flow (Cycle Canceling) | supplycm Algorithm Library"
description: "Plain-English explanation of min_cost_flow_cycle_canceling from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, min_cost_flow_cycle_canceling, supply chain, plain english, networks"
---

# Min-Cost Flow (Cycle Canceling)

> **Call it:** `from supplycm.network import min_cost_flow_cycle_canceling` · **Level:** Advanced · **You need:** basic arithmetic only

Max flow told you HOW MUCH can move; min-cost flow asks the next question: at what CHEAPEST total cost? This version starts with a feasible flow and cancels costly loops - rerouting any cycle whose cancellation saves money - until no improvement remains.

**Think of it like this:** Rerouting delivery vans around circular wasteful loops: keep canceling any round trip that burns money, until every remaining loop is already optimal.

## When to reach for it

- Shipping plans with per-lane costs and capacity limits
- Turning a feasible plan into an economical one

## Try it with supplycm

```python
from supplycm.network import min_cost_flow_cycle_canceling

result = min_cost_flow_cycle_canceling(capacity=[[0, 2, 2, 0], [0, 0, 0, 2], [0, 0, 0, 2], [0, 0, 0, 0]], costs=[[0, 1, 3, 0], [0, 0, 0, 1], [0, 0, 0, 1], [0, 0, 0, 0]], supply=[2, 0, 0, -2])
print(result)
```

You should see something like:

```text
4.0
```

The minimum total cost of moving the required supply - the plan now exploits cheap lanes to their limits before touching pricey ones.

## Check yourself

1. What is a 'negative cost cycle'?
2. How does this differ from max flow?
3. Where does this appear in logistics?

<details>
<summary>Show answers</summary>

1. A loop you could reroute flow around and SAVE money - canceling them is the whole optimization.

2. Max flow maximizes quantity; min-cost flow achieves a REQUIRED quantity at minimum cost - different questions, related machinery.

3. Multi-lane freight assignment with capacities - the workhorse behind network flow planning modules.

</details>

## Try this now

Swap two lane costs and re-run; identify which cancellation loop appears and what it reroutes.

---
[← Stoer-Wagner Global Min Cut](min_cut_stoer_wagner.md) · [Back to Networks library](README.md) · [Successive Shortest Path (Min-Cost Flow) →](successive_shortest_path.md)
