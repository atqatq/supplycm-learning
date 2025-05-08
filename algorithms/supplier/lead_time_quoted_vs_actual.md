---
title: "Lead Time: Quoted vs Actual | supplycm Algorithm Library"
description: "Plain-English explanation of lead_time_quoted_vs_actual from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, lead_time_quoted_vs_actual, supply chain, plain english, supplier & procurement"
---

# Lead Time: Quoted vs Actual

> **Call it:** `from supplycm.supplier import lead_time_quoted_vs_actual` · **Level:** Intermediate · **You need:** basic arithmetic only

Compares what suppliers promise with what they deliver: feed pairs of (quoted, actual) lead times and get the average quoted, the average actual, and the gap. Persistent gaps mean your planning assumptions are quietly wrong - and your reorder points are wrong with them.

**Think of it like this:** A GPS that says 30 minutes but always takes 40 - after ten trips you stop trusting the estimate, and you should.

## When to reach for it

- Auditing planning parameters against supplier reality
- Deciding whether to renegotiate lead times or pad them internally

## Try it with supplycm

```python
from supplycm.supplier import lead_time_quoted_vs_actual

result = lead_time_quoted_vs_actual(lead_times=[(10, 12), (10, 11), (14, 18), (7, 7), (10, 13)])
print(result)
```

You should see something like:

```text
[10.2, 12.2, 2.0]
```

Quoted averages about 10 days, actual about 12 - a systematic 2-day gap that belongs in your reorder point math.

## Check yourself

1. Which is more damaging: a 2-day bias or occasional 10-day spikes?
2. Who should own closing this gap?
3. Where should the 'actual' number end up?

<details>
<summary>Show answers</summary>

1. Both hurt differently - bias shifts every order late; spikes cause rare deep stockouts. Fix bias first, buffer for spikes.

2. Purchasing owns the conversation; planning owns the parameter change if the gap persists.

3. In your ERP lead time fields - plans built on quoted numbers inherit every miss.

</details>

## Try this now

Compute the gap for 8 (quoted, actual) pairs; state whether to change the system parameter or the supplier contract.

---
[← On-Time Delivery Rate](on_time_delivery_rate.md) · [Back to Supplier & Procurement library](README.md) · [Purchase Order Compliance →](purchase_order_compliance.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
