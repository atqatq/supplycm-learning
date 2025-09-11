---
title: "Cycle Service Level from Safety Stock | supplycm Algorithm Library"
description: "Plain-English explanation of cycle_service_level from the supplycm Inventory module, with a runnable Python example and self-check questions."
keywords: "supplycm, inventory, cycle_service_level, supply chain, plain english, inventory"
---

# Cycle Service Level from Safety Stock

> **Call it:** `from supplycm.inventory import cycle_service_level` · **Level:** Advanced · **You need:** basic arithmetic only

This works BACKWARDS from stock to service: given the safety stock you hold, what cycle service level does it actually deliver? It is the honesty check - planners claim 98% service, the math on their buffers sometimes says 87%.

**Think of it like this:** A rain gauge for your umbrella cabinet: it tells you what weather your current umbrella stash actually handles.

## When to reach for it

- Auditing whether stated service levels match real buffers
- Deciding whether current safety stock is over- or under-sized

## Try it with supplycm

```python
from supplycm.inventory import cycle_service_level

result = cycle_service_level(safety_stock=30, demand_std=12, lead_time=4)
print(result)
```

You should see something like:

```text
0.8944
```

A z-equivalent above the target - roughly 98% service; shrink the cushion to 20 and watch the implied service drop.

## Check yourself

1. What is 'cycle service level' exactly?
2. Safety stock 0 gives what service level?
3. You need 99% but hold 90%-level stock. Options?

<details>
<summary>Show answers</summary>

1. The chance of NOT stocking out during one replenishment cycle - not the share of units served (that's fill rate).

2. 50% - you cover average demand only, so half the cycles fall short.

3. Raise the buffer, cut lead-time/demand variability, or honestly re-negotiate the promise.

</details>

## Try this now

Reverse-engineer the service level of three real items' safety stock; rank them by how misleading their labels are.

---
[← Demand During Lead Time](demand_during_lead_time.md) · [Back to Inventory library](README.md) · [Fill Rate Calculation →](fill_rate_calculation.md)
