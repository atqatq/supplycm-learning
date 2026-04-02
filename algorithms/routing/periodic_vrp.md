---
title: "Periodic VRP | supplycm Algorithm Library"
description: "Plain-English explanation of periodic_vrp from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, periodic_vrp, supply chain, plain english, routing & transportation"
---

# Periodic VRP

> **Call it:** `from supplycm.routing import periodic_vrp` · **Level:** Advanced · **You need:** basic arithmetic only

Some customers need visits on SCHEDULES - twice a week, say - but the exact days are your choice. Periodic VRP assigns visit-day patterns AND builds daily routes: today's plan serves everyone whose pattern includes today. The milk-round problem, formalized.

**Think of it like this:** A doctor's round planning: some patients need twice-weekly visits - choose WHICH days for whom so every day's round stays compact.

## When to reach for it

- Weekly delivery patterns to repeat customers
- Service visits (vending, maintenance) with frequency requirements

## Try it with supplycm

```python
from supplycm.routing import periodic_vrp

result = periodic_vrp(customers=[(1, 1, 1, 2), (2, 2, 1, 2), (3, 1, 1, 2)], days=4)
print(result)
```

You should see something like:

```text
[[0, 1, 2], [], [0, 1, 2], []]
```

A route list per day - each customer appears on exactly their pattern's days; daily routes stay compact while frequency promises hold.

## Check yourself

1. What two decisions does periodic VRP add?
2. Why does pattern choice matter so much?
3. What does flexibility in patterns buy?

<details>
<summary>Show answers</summary>

1. Pattern assignment (which days per customer) and daily routing - they interact and must be planned together.

2. Serving all Monday-heavy patterns together drowns that day - spreading patterns smooths daily load like slotting smooths waves.

3. Leveling: customers who accept 'any two days' become shock absorbers - the planner's secret weapon.

</details>

## Try this now

Spread three twice-weekly customers across 4 days so no day carries all three; verify daily route counts.

---
[← Multi-Depot VRP](multi_depot_vrp.md) · [Back to Routing & Transportation library](README.md) · [Pickup and Delivery Problem (PDP) →](pickup_delivery_problem.md)
