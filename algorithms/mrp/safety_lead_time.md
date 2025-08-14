---
title: "Safety Lead Time | supplycm Algorithm Library"
description: "Plain-English explanation of safety_lead_time from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, safety_lead_time, supply chain, plain english, mrp & production planning"
---

# Safety Lead Time

> **Call it:** `from supplycm.mrp import safety_lead_time` · **Level:** Beginner · **You need:** basic arithmetic only

Safety lead time is a buffer in TIME, not units: order earlier than the standard lead time says. If parts usually take 10 days and you plan 12, orders release 2 days early - protecting due dates against ordinary lateness without inflating order sizes.

**Think of it like this:** Leaving for the airport 30 minutes 'early' every time - same route, same traffic, calmer arrival.

## When to reach for it

- Suppliers with mildly unreliable delivery timing
- Stable demand where a stock buffer would sit idle

## Try it with supplycm

```python
from supplycm.mrp import safety_lead_time

result = safety_lead_time(standard_lead_time=10, safety_lead=2)
print(result)
```

You should see something like:

```text
12
```

12 - the planning system will now release orders two days earlier than the supplier's promise.

## Check yourself

1. Safety lead time vs safety stock - what's the difference?
2. When is safety lead time the cheaper protection?
3. Supplier improves to near-perfect timing. Action?

<details>
<summary>Show answers</summary>

1. Time buffer vs quantity buffer: release earlier vs hold more. Pick based on whether lateness or variability dominates.

2. Steady demand with unreliable timing - extra stock would just sit, while early release costs almost nothing.

3. Remove the buffer gradually - permanent cushions hide real performance forever.

</details>

## Try this now

A 15-day lead time runs 1-2 days late most months. Set safety lead time and state what changes in release dates.

---
[← Shrinkage Factor](shrinkage_factor.md) · [Back to MRP & Production Planning library](README.md) · [Lead Time Offsetting →](lead_time_offsetting.md)
