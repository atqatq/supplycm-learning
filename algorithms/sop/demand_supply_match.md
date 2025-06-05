---
title: "Demand-Supply Match | supplycm Algorithm Library"
description: "Plain-English explanation of demand_supply_match from the supplycm S&OP module, with a runnable Python example and self-check questions."
keywords: "supplycm, sop, demand_supply_match, supply chain, plain english, s&op"
---

# Demand-Supply Match

> **Call it:** `from supplycm.sop import demand_supply_match` · **Level:** Beginner · **You need:** basic arithmetic only

This compares your demand plan against your supply plan, period by period, and shows the gaps: where you are short (demand beats supply) and where you build excess (supply beats demand). It is the heart of every monthly S&OP meeting - one table everyone can argue about productively.

**Think of it like this:** A scale comparing two suitcases before the flight: it shows exactly which side is heavier and by how much.

## When to reach for it

- Preparing the gap view for a monthly S&OP review
- Spotting which months need overtime, pre-builds, or demand shaping

## Try it with supplycm

```python
from supplycm.sop import demand_supply_match

result = demand_supply_match(demand=[100, 120, 140, 130], supply=[110, 110, 110, 130])
print(result)
```

You should see something like:

```text
[[-10, 10, 30, 0], [-10.0, 0.0, 30.0, 30.0]]
```

Two lists appear - shortfalls where demand outruns supply and surpluses where it does not; month 2 is the tight one to fix.

## Check yourself

1. What are the two gap directions and their risks?
2. Demand exceeds supply in month 3. Name two honest fixes.
3. Who belongs in the room when gaps appear?

<details>
<summary>Show answers</summary>

1. Short (missed sales, firefighting) and surplus (cash on shelves, markdowns).

2. Pull production forward / add capacity, or shape demand - raise price, defer promotions, pre-book orders.

3. Sales, operations, and finance together - S&OP is the meeting where those gaps get settled.

</details>

## Try this now

Build a 6-month demand plan with a July peak and a flat supply plan; identify the two gap months and one fix for each.

---
[Back to S&OP library](README.md) · [Chase Strategy →](production_chase_strategy.md)

*New to this topic? Start with the core lesson first: [09_planning.md](../../modules/09_planning.md).*
