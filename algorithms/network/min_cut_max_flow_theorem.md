---
title: "Min-Cut / Max-Flow Theorem | supplycm Algorithm Library"
description: "Plain-English explanation of min_cut_max_flow_theorem from the supplycm Networks module, with a runnable Python example and self-check questions."
keywords: "supplycm, network, min_cut_max_flow_theorem, supply chain, plain english, networks"
---

# Min-Cut / Max-Flow Theorem

> **Call it:** `from supplycm.network import min_cut_max_flow_theorem` · **Level:** Advanced · **You need:** basic arithmetic only

The theorem behind max flow: the maximum flow exactly equals the capacity of the cheapest 'cut' - the smallest set of lanes whose removal disconnects source from sink. This finds that critical cut: your network's true bottleneck, made visible.

**Think of it like this:** Finding the narrowest mountain pass controlling all trade: no matter how good the roads elsewhere, the pass's width IS your throughput.

## When to reach for it

- Locating the true bottleneck of a network
- Justifying capacity investments with the exact binding constraint

## Try it with supplycm

```python
from supplycm.network import min_cut_max_flow_theorem

result = min_cut_max_flow_theorem(capacity=[[0, 5, 0, 0], [0, 0, 4, 3], [0, 0, 0, 2], [0, 0, 0, 0]], source=0, sink=3)
print(result)
```

You should see something like:

```text
[5.0, [0]]
```

The cut capacity and the nodes on the source side - the lanes crossing from that set to the rest ARE the bottleneck.

## Check yourself

1. What does 'min cut = max flow' actually mean?
2. How is the cut useful beyond the number?
3. After widening the bottleneck, what happens?

<details>
<summary>Show answers</summary>

1. Perfection: no flow can beat the narrowest cut, and some flow achieves exactly it - the ceiling and the best attempt coincide.

2. It NAMES the binding lanes - investment goes there, not to politically loud but non-binding lanes.

3. A different cut becomes minimum - bottlenecks migrate; capacity planning is a chain of these discoveries.

</details>

## Try this now

Widen the found cut by one unit and recompute; name the new bottleneck set and reflect on the whack-a-mole.

---
[← Edmonds-Karp Max Flow](edmonds_karp_max_flow.md) · [Back to Networks library](README.md) · [Stoer-Wagner Global Min Cut →](min_cut_stoer_wagner.md)
