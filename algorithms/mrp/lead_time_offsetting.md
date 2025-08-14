---
title: "Lead Time Offsetting | supplycm Algorithm Library"
description: "Plain-English explanation of lead_time_offsetting from the supplycm MRP & Production Planning module, with a runnable Python example and self-check questions."
keywords: "supplycm, mrp, lead_time_offsetting, supply chain, plain english, mrp & production planning"
---

# Lead Time Offsetting

> **Call it:** `from supplycm.mrp import lead_time_offsetting` · **Level:** Beginner · **You need:** basic arithmetic only

If a part needs 3 weeks and you must HAVE it in week 8, the ORDER must release in week 5. Offsetting shifts planned receipts back by the lead time - the simple move that turns 'what we need' into 'when we must act'.

**Think of it like this:** A birthday cake due Saturday from a bakery that needs 2 days' notice: you must call by Thursday.

## When to reach for it

- Converting MRP planned receipts into planned order release dates
- Explaining to buyers why the system nags them TODAY about next month

## Try it with supplycm

```python
from supplycm.mrp import lead_time_offsetting

result = lead_time_offsetting(planned_receipts=[0, 0, 100, 0, 200], lead_time=2)
print(result)
```

You should see something like:

```text
[100.0, 0.0, 200.0, 0.0, 0.0]
```

Receipts in weeks 3 and 5 become releases in weeks 1 and 3 - those are the weeks the buyer must actually act.

## Check yourself

1. Lead time 2 means the release lands where?
2. Release date falls in the past. What does that mean?
3. Two components, lead times 1 and 4, same due date. Which nags first?

<details>
<summary>Show answers</summary>

1. Two periods before the need date - receipt week minus 2.

2. You are already late - expedite, reduce the requirement, or accept a miss; the system is telling the truth.

3. The 4-week one - offsetting is per component, so plans release at different times.

</details>

## Try this now

Receipts needed weeks 4 and 7, lead time 3. Compute release weeks and check the function agrees.

---
[← Safety Lead Time](safety_lead_time.md) · [Back to MRP & Production Planning library](README.md) · [Backflush →](backflush.md)
