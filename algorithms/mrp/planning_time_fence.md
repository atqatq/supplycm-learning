---
title: "Planning Time Fence | supplycm Algorithm Library"
description: "Plain-English explanation of planning_time_fence from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, planning_time_fence, supply chain, plain english, mrp & production planning"
---

# Planning Time Fence

> **Call it:** `from supplycm.mrp import planning_time_fence` · **Level:** Intermediate · **You need:** basic arithmetic only

Inside the planning time fence, the system stops changing lot sizes automatically: it plans lot-for-lot inside, fixed-lot outside. This keeps near-term schedules steady while far-out periods stay economically sized - a quieter, stabler MRP output.

**Think of it like this:** In the last week before moving house you only fix essentials; the big furniture decisions were made months ago.

## When to reach for it

- Reducing nervous MRP messages that whipsaw the shop floor
- Sites where schedule stability matters as much as cost

## Try it with supplycm

```python
from supplycm.mrp import planning_time_fence

result = planning_time_fence(demands=[10, 20, 30, 40], fence_period=2, lot_size_fenced=10, lot_size_open=50)
print(result)
```

You should see something like:

```text
[10, 20, 30, 40]
```

Inside the fence (periods 1-2) quantities stay tight; outside they come in lots of 50 - stability near, economy far.

## Check yourself

1. Planning fence vs demand fence - what does each control?
2. Why plan lot-for-lot inside the fence?
3. Fence too far out - symptom?

<details>
<summary>Show answers</summary>

1. Demand fence controls WHAT demand counts; planning fence controls HOW lot sizes are chosen.

2. To avoid big rigid lots churning near-term capacity - flexibility first when the time is short.

3. The plan gets rigid and unresponsive; too near - MRP stays nervous. Tune by watching message churn.

</details>

## Try this now

Move the fence from period 2 to 3 on the example and describe which messages disappear.

---
[← Demand Time Fence](demand_time_fence.md) · [Back to MRP & Production Planning library](README.md) · [Pegging →](pegging.md)
