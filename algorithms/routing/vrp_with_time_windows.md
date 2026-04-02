---
title: "VRP with Time Windows | supplycm Algorithm Library"
description: "Plain-English explanation of vrp_with_time_windows from the supplycm Routing & Transportation module, with a runnable Python example and self-check questions."
keywords: "supplycm, routing, vrp_with_time_windows, supply chain, plain english, routing & transportation"
---

# VRP with Time Windows

> **Call it:** `from supplycm.routing import vrp_with_time_windows` · **Level:** Advanced · **You need:** basic arithmetic only

Customers demand service within windows - 'between 9 and 11' - and the route must arrive inside them, waiting if early. This builds routes respecting capacity AND every window. Waiting time, sequencing pressure, and feasibility collide: real delivery planning starts here.

**Think of it like this:** A day of appointments: each client has a bookable slot, traffic eats travel time, and you must keep every promise or wait politely outside.

## When to reach for it

- Home delivery slots, business receiving hours
- Any schedule where WHEN matters as much as WHERE

## Try it with supplycm

```python
from supplycm.routing import vrp_with_time_windows

result = vrp_with_time_windows(distances=[[0, 10, 15, 20], [10, 0, 35, 25], [15, 35, 0, 30], [20, 25, 30, 0]], demands=[0, 1, 1, 1], time_windows=[(0, 100), (0, 10), (0, 20), (0, 30)], service_times=[0, 1, 1, 1], vehicle_capacity=3)
print(result)
```

You should see something like:

```text
[[0, 1, 0], [0, 2, 0], [0, 3, 0]]
```

Feasible routes per vehicle - each customer's arrival (travel + wait) lands inside its window; infeasible customers force more vehicles.

## Check yourself

1. What new tension do time windows add?
2. Why do vehicles proliferate under tight windows?
3. What should you negotiate first when infeasible?

<details>
<summary>Show answers</summary>

1. Distance wants compact routes; windows dictate order - the shortest-feeling route can violate a promise, and vice versa.

2. Feasibility, not capacity, binds: when 'by 10am' crowds the morning, extra vehicles buy time slots, not weight.

3. Window widths - widening one window by an hour often saves a whole vehicle; that's the highest-leverage phone call.

</details>

## Try this now

Widen one customer's window from (0,10) to (0,20) and rerun; trace which route stitched back together.

---
[← Split Delivery VRP](split_delivery_vrp.md) · [Back to Routing & Transportation library](README.md) · [Multi-Depot VRP →](multi_depot_vrp.md)
