---
title: "Facility Location (Fixed Cost) | supplycm Algorithm Library"
description: "Plain-English explanation of facility_location_fixed_cost from the supplycm Network Design module, with a runnable Python example and self-check questions."
keywords: "supplycm, network_design, facility_location_fixed_cost, supply chain, plain english, network design"
---

# Facility Location (Fixed Cost)

> **Call it:** `from supplycm.network_design import facility_location_fixed_cost` · **Level:** Advanced · **You need:** basic arithmetic only

The real siting problem: each candidate warehouse has a fixed opening cost, shipping costs vary by lane, and you can't open everything. This selects WHICH facilities to open and assigns demand to minimize total cost - opening costs and shipping together.

**Think of it like this:** Choosing which restaurants to franchise in a region: each opening costs money up front, but every closed gap raises delivery miles - the math balances both.

## When to reach for it

- Network design: how many DCs, where, serving whom
- Any build-vs-ship trade-off across candidate sites

## Try it with supplycm

```python
from supplycm.network_design import facility_location_fixed_cost

result = facility_location_fixed_cost(demands=[100, 80, 120], distances=[[10, 40, 50], [40, 10, 30], [50, 30, 8]], fixed_costs=[5000, 4000, 6000], num_facilities=2)
print(result)
```

You should see something like:

```text
[[1, 0], 14400]
```

Chosen facilities and total cost - watch whether opening the third (cheap shipping, pricey fixed) would have paid for itself.

## Check yourself

1. What two cost families does this model weigh?
2. Why can the optimum be 'open fewer than all candidates'?
3. What happens when demand grows 50%?

<details>
<summary>Show answers</summary>

1. Fixed opening costs (fewer sites, save money) versus variable shipping (more sites, shorter hauls).

2. Beyond some point, each extra site's fixed cost exceeds the shipping it saves - the curve flattens, then reverses.

3. Shipping penalties for distance rise, tipping more sites into 'worth opening' - networks re-optimize as scale shifts.

</details>

## Try this now

Re-solve allowing 3 facilities; find the demand level where the third site finally earns its keep.

---
[← Center of Gravity Location](center_of_gravity.md) · [Back to Network Design library](README.md) · [Network Reliability →](network_reliability.md)
