---
title: "Stoer-Wagner Global Min Cut | supplycm Algorithm Library"
description: "Plain-English explanation of min_cut_stoer_wagner from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, min_cut_stoer_wagner, supply chain, plain english, networks"
---

# Stoer-Wagner Global Min Cut

> **Call it:** `from supplycm.network import min_cut_stoer_wagner` · **Level:** Advanced · **You need:** basic arithmetic only

Instead of separating one source from one sink, find the CHEAPEST way to split the entire network into two parts - anywhere. It reveals the fault line the whole network would crack along: the global weak point, no source-sink assumptions needed.

**Think of it like this:** Finding where a sheet of paper tears most easily - not between two chosen points, just its structurally weakest line, anywhere.

## When to reach for it

- Network partitioning and vulnerability analysis
- Finding the intrinsic weak seam of a distribution network

## Try it with supplycm

```python
from supplycm.network import min_cut_stoer_wagner

result = min_cut_stoer_wagner(weights=[[0, 3, 3, 0], [3, 0, 1, 2], [3, 1, 0, 2], [0, 2, 2, 0]])
print(result)
```

You should see something like:

```text
[4, [3]]
```

The cut weight and one side's nodes - the cheapest way this network naturally splits in two, wherever it lies.

## Check yourself

1. Global min cut vs s-t min cut - difference?
2. What does the global weak seam mean for a supply network?
3. How do you harden a weak seam?

<details>
<summary>Show answers</summary>

1. No chosen endpoints - the weakest split ANYWHERE; s-t versions only look at lines between two named nodes.

2. The natural fracture line under stress - where regional disruption would split the network first.

3. Add capacity across it or duplicate the flow role on both sides - make the crack expensive to propagate.

</details>

## Try this now

Locate the seam, then add one cross-seam lane and re-run; measure how much tougher the network became.

---
[← Min-Cut / Max-Flow Theorem](min_cut_max_flow_theorem.md) · [Back to Networks library](README.md) · [Min-Cost Flow (Cycle Canceling) →](min_cost_flow_cycle_canceling.md)
