---
title: "Dial-a-Ride | supplycm Algorithm Library"
description: "Plain-English explanation of dial_a_ride from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, dial_a_ride, supply chain, plain english, routing & transportation"
---

# Dial-a-Ride

> **Call it:** `from supplycm.routing import dial_a_ride` · **Level:** Advanced · **You need:** basic arithmetic only

PDP with passengers: each request specifies pickup point, drop-off point, and how many ride - like patient transport or shared shuttles. Routes must respect pairing, capacity, and humane ride times. The logistics of moving PEOPLE, with their comfort along for the ride.

**Think of it like this:** A hospital shuttle dispatcher: every patient has a from, a to, and a dignity threshold - no one rides in circles for an hour.

## When to reach for it

- Patient transport, airport shuttles, paratransit
- Any shared-ride service with pickup-delivery pairs

## Try it with supplycm

```python
from supplycm.routing import dial_a_ride

result = dial_a_ride(requests=[(1, 2, 1, 5), (3, 4, 2, 8)], distances=[[0, 5, 9, 8], [5, 0, 4, 3], [9, 4, 0, 6], [8, 3, 6, 0]], vehicle_capacity=2)
print(result)
```

You should see something like:

```text
[[0, 1, 2, 0, 3, 4]]
```

The routes serving all requests - each passenger's pickup precedes their drop-off within vehicle capacity.

## Check yourself

1. What do human passengers add over freight?
2. What is 'ride time' and why bound it?
3. How does capacity interact with pairs?

<details>
<summary>Show answers</summary>

1. Service expectations - ride-time limits, punctuality, and dignity constraints that pure cargo never complains about.

2. Minutes between a passenger's pickup and drop-off - unbounded, a cheap route tours the city with someone aboard; bounded, routes stay humane.

3. Load rises at pickups, falls at drop-offs - the vehicle's peak onboard count, not total demand, must fit.

</details>

## Try this now

Track onboard passengers stop by stop in the output; find the moment of peak load and confirm it stayed legal.

---
[← Pickup and Delivery Problem (PDP)](pickup_delivery_problem.md) · [Back to Routing & Transportation library](README.md) · [Eulerian Tour →](eulerian_tour.md)
