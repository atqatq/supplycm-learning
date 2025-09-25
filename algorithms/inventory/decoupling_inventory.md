---
title: "Decoupling Inventory | supplycm Algorithm Library"
description: "Plain-English explanation of decoupling_inventory from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, decoupling_inventory, supply chain, plain english, inventory"
---

# Decoupling Inventory

> **Call it:** `from supplycm.inventory import decoupling_inventory` · **Level:** Intermediate · **You need:** basic arithmetic only

Decoupling stock sits BETWEEN stages that run at different rhythms, letting each operate independently - fast downstream not starved by slow upstream. The function sizes the buffer from the two stages' rates and the protection time. It is the shock absorber of production flow.

**Think of it like this:** A water tower between the pump and the houses: the pump can service its own schedule while taps run whenever they want.

## When to reach for it

- Buffering between machining and assembly running different paces
- Isolating a bottleneck stage from upstream hiccups

## Try it with supplycm

```python
from supplycm.inventory import decoupling_inventory

result = decoupling_inventory(upstream_rate=90, downstream_rate=110, buffer_time=4)
print(result)
```

You should see something like:

```text
80
```

80 units of buffer - enough to run the faster downstream stage through the protection window despite the slower feeder.

## Check yourself

1. What breaks when decoupling stock runs dry?
2. Where does decoupling stock belong in a factory?
3. How is this different from WIP?

<details>
<summary>Show answers</summary>

1. The downstream stage starves and stops - the buffer bought independence, and its absence restores dependence abruptly.

2. Between stages with mismatched rates or reliability - and always ahead of the constraint to keep it busy.

3. WIP is work caught mid-process; decoupling stock is deliberate buffer inventory between processes.

</details>

## Try this now

Size the buffer between a 60/hr upstream and 75/hr downstream with 6 hours of protection - then halve buffer_time and watch it shrink.

---
[← Anticipation Inventory](anticipation_inventory.md) · [Back to Inventory library](README.md) · [Newsvendor Model →](newsvendor_model.md)
