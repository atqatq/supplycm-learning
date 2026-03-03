---
title: "Single-Source Allocation | supplycm Algorithm Library"
description: "Plain-English explanation of single_source_allocation from the supplycm Network Design module, with a runnable Python example and self-check questions."
keywords: "supplycm, network_design, single_source_allocation, supply chain, plain english, network design"
---

# Single-Source Allocation

> **Call it:** `from supplycm.network_design import single_source_allocation` · **Level:** Advanced · **You need:** basic arithmetic only

Each customer must be served by exactly ONE facility - no splitting shipments. Given distances and facility capacities, this assigns every customer to a workable single source. Real-world constraint, real mathematical bite.

**Think of it like this:** Assigning every student exactly one homeroom: capacity limits, distance matters, and no splitting kids across rooms.

## When to reach for it

- Territory design: which DC serves which region exclusively
- Account assignments where single-sourcing is contractual

## Try it with supplycm

```python
from supplycm.network_design import single_source_allocation

result = single_source_allocation(demands=[100, 80, 120], distances=[[10, 40, 50], [40, 10, 30], [50, 30, 8]], capacities=[200, 150, 100])
print(result)
```

You should see something like:

```text
[0, 2, 1]
```

One source per customer - check who got squeezed to their second choice by capacity, and at what distance cost.

## Check yourself

1. Why does single-sourcing complicate optimization?
2. What does single-sourcing buy operationally?
3. How would you relax it if capacities strain?

<details>
<summary>Show answers</summary>

1. No splitting means assignments interact - one big customer's choice can evict another from their best source.

2. Simpler relationships, cleaner accountability, easier returns - worth real money despite the distance penalty.

3. Allow one big customer to dual-source - the math softens immediately; that's the negotiation lever.

</details>

## Try this now

Tighten one facility's capacity by 30% and observe which customers migrate - trace the cascade.

---
[← Network Reliability](network_reliability.md) · [Back to Network Design library](README.md)
