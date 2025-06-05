---
title: "Chase Strategy | supplycm Algorithm Library"
description: "Plain-English explanation of production_chase_strategy from the supplycm S&OP module, with a runnable Python example and self-check questions."
keywords: "supplycm, sop, production_chase_strategy, supply chain, plain english, s&op"
---

# Chase Strategy

> **Call it:** `from supplycm.sop import production_chase_strategy` · **Level:** Beginner · **You need:** basic arithmetic only

The chase strategy makes production follow demand exactly: 120 demanded means 120 produced, and inventory stays flat. Overtime, temp workers, and flexible shifts absorb the ups and downs. You never carry extra stock - but your workforce plan swings wildly.

**Think of it like this:** A delivery rider matching every traffic wave - always exactly in sync, but exhausting.

## When to reach for it

- Perishables or custom products where inventory is not an option
- Seasonal businesses with easy access to flexible labor

## Try it with supplycm

```python
from supplycm.sop import production_chase_strategy

result = production_chase_strategy(demand=[100, 150, 80, 120], initial_inventory=0, safety_stock=0)
print(result)
```

You should see something like:

```text
[100, 150, 80, 120]
```

Production equals demand every period - inventory never builds, but the workforce must flex by 70 units between months.

## Check yourself

1. What does chase do to inventory and to workforce stress?
2. When is chase the obvious choice?
3. What does a chase plan look like in peak season hiring?

<details>
<summary>Show answers</summary>

1. Inventory stays minimal; workforce/capacity stress peaks because output must flex every period.

2. Fresh food, made-to-order, or when holding stock is costlier than flexing capacity.

3. Hire temps ahead of the ramp, then release them - expensive and socially costly if extreme.

</details>

## Try this now

Produce a chase plan for demand [80, 160, 200, 60] and list two operational consequences of the swings.

---
[← Demand-Supply Match](demand_supply_match.md) · [Back to S&OP library](README.md) · [Level Strategy →](production_level_strategy.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
