---
title: "Negotiation Zone (ZOPA) | supplycm Algorithm Library"
description: "Plain-English explanation of negotiation_zone from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, negotiation_zone, supply chain, plain english, supplier & procurement"
---

# Negotiation Zone (ZOPA)

> **Call it:** `from supplycm.supplier import negotiation_zone` · **Level:** Intermediate · **You need:** basic arithmetic only

Given each side's walk-away price, this finds the zone of possible agreement and whether it exists at all. If the buyer won't pay more than 90 and the seller won't take less than 95, there is no deal to be had - better to know before the meeting.

**Think of it like this:** House hunting: your max, their minimum, and the overlap where a handshake lives.

## When to reach for it

- Preparing price negotiations with a clear walk-away discipline
- Deciding whether to negotiate at all or expand the pie (scope, terms, volume)

## Try it with supplycm

```python
from supplycm.supplier import negotiation_zone

result = negotiation_zone(buyer_walkaway=95.0, supplier_walkaway=80.0)
print(result)
```

You should see something like:

```text
[80.0, 95.0, True]
```

A zone exists from 80 to 95 - everything inside is winnable; the buyer's job is anchoring low, the supplier's is anchoring high.

## Check yourself

1. What is a walk-away price?
2. No zone exists. What are your options?
3. Why should your walk-away stay private?

<details>
<summary>Show answers</summary>

1. The point where walking out beats dealing - your Best Alternative (BATNA) defines it.

2. Change the deal itself: volumes, payment terms, specs, timing - expand the pie until zones overlap, or accept no deal.

3. Once revealed, the other side only ever offers just above it.

</details>

## Try this now

You can pay 120; the supplier's floor is 115. Where do you anchor, and what non-price item might widen the zone?

---
[← Supplier Diversity Index](supplier_diversity_index.md) · [Back to Supplier & Procurement library](README.md) · [Competitive Bidding →](competitive_bidding.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
