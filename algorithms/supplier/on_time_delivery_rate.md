---
title: "On-Time Delivery Rate | supplycm Algorithm Library"
description: "Plain-English explanation of on_time_delivery_rate from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, on_time_delivery_rate, supply chain, plain english, supplier & procurement"
---

# On-Time Delivery Rate

> **Call it:** `from supplycm.supplier import on_time_delivery_rate` · **Level:** Beginner · **You need:** basic arithmetic only

The workhorse supplier metric: of all deliveries, what share arrived on time? Feed it pairs of (promised date, actual date) and get one percentage. It is simple, brutal, and the first chart to show a supplier slipping.

**Think of it like this:** An airline's on-time stats: one number passengers actually feel, whatever the excuses.

## When to reach for it

- Monthly supplier performance reviews
- Triggering escalations when OTD falls below contract levels

## Try it with supplycm

```python
from supplycm.supplier import on_time_delivery_rate

result = on_time_delivery_rate(deliveries=[(10, 9), (10, 12), (15, 15), (20, 22), (25, 24)])
print(result)
```

You should see something like:

```text
0.6
```

60% on-time - three of five deliveries missed their promise, and each miss had downstream costs the supplier never sees.

## Check yourself

1. What counts as 'on time' - early too?
2. OTD fell from 95% to 85%. First questions?
3. Why does OTD drive your safety stock?

<details>
<summary>Show answers</summary>

1. Usually promised-or-before, but very early can also hurt (storage, expiry). Define it in the contract.

2. Which products/lanes slipped, and is it capacity, quality holds, or data errors? Segment before you accuse.

3. Late deliveries behave like demand spikes - you buffer stock against the supplier's unreliability.

</details>

## Try this now

Score 10 deliveries you invent; compute OTD, then explain what a 70% rate would do to your reorder points.

---
[← Vendor Scorecard](vendor_scorecard.md) · [Back to Supplier & Procurement library](README.md) · [Lead Time: Quoted vs Actual →](lead_time_quoted_vs_actual.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
