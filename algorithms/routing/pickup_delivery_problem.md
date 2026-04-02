---
title: "Pickup and Delivery Problem (PDP) | supplycm Algorithm Library"
description: "Plain-English explanation of pickup_delivery_problem from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, pickup_delivery_problem, supply chain, plain english, routing & transportation"
---

# Pickup and Delivery Problem (PDP)

> **Call it:** `from supplycm.routing import pickup_delivery_problem` · **Level:** Advanced · **You need:** basic arithmetic only

Ride-sharing for freight: every request has a pickup AND a delivery stop, and the pickup MUST precede its delivery on the same route. This builds routes honoring those pairs - the floor plan of couriers, dial-a-ride, and backhaul logistics.

**Think of it like this:** A taxi shift: every passenger boards before they alight - and the same car serves both ends. Sequencing becomes a promise-keeping exercise.

## When to reach for it

- Courier and same-day delivery operations
- Reverse flows: collecting returns while delivering fresh goods

## Try it with supplycm

```python
from supplycm.routing import pickup_delivery_problem

result = pickup_delivery_problem(distances=[[0, 4, 1, 9], [4, 0, 6, 2], [1, 6, 0, 8], [9, 2, 8, 0]], pickup_pairs=[(1, 2)])
print(result)
```

You should see something like:

```text
[0, 1, 2, 0]
```

The route with pairing respected - pickup stop precedes its delivery stop; break that rule and the route is fantasy.

## Check yourself

1. What constraint defines a PDP route?
2. How does load tracking change?
3. Where do backhauls fit in?

<details>
<summary>Show answers</summary>

1. Pairing precedence: for every request, pickup before delivery, same vehicle - everything else is negotiation.

2. Capacity now fluctuates stop by stop - goods ride along between their pickup and delivery, so the peak load matters, not the total.

3. As paired requests where the 'pickup' is a return at a delivery customer - one route serves both directions of commerce.

</details>

## Try this now

Trace the route and verify the pair order; then add a second pair and check the capacity profile never exceeds the van.

---
[← Periodic VRP](periodic_vrp.md) · [Back to Routing & Transportation library](README.md) · [Dial-a-Ride →](dial_a_ride.md)
