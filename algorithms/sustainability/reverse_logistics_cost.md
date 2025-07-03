---
title: "Reverse Logistics Cost | supplycm Algorithm Library"
description: "Plain-English explanation of reverse_logistics_cost from the supplycm Sustainability module, with a runnable Python example and self-check questions."
keywords: "supplycm, sustainability, reverse_logistics_cost, supply chain, plain english, sustainability"
---

# Reverse Logistics Cost

> **Call it:** `from supplycm.sustainability import reverse_logistics_cost` · **Level:** Beginner · **You need:** basic arithmetic only

Returns are a supply chain running backwards: transport back, inspection, reprocessing, disposal of the hopeless, minus what you resell. This function nets all of it out per returned unit's share, so 'free returns' shows its true price.

**Think of it like this:** A Revolving Door: every customer who walks back through carries a cost ticket - some bring money back, some bring only paperwork.

## When to reach for it

- Pricing the real cost of a returns-friendly policy
- Deciding whether a returned unit is worth restocking, refurbishing, or scrapping

## Try it with supplycm

```python
from supplycm.sustainability import reverse_logistics_cost

result = reverse_logistics_cost(return_rate=0.08, unit_cost=40.0, processing_cost=6.0, disposal_cost=3.0, resale_value=35.0)
print(result)
```

You should see something like:

```text
0.51
```

The net result shows returns quietly eating several points of margin - enough to rethink 'free returns' on low-margin lines.

## Check yourself

1. Name the four cost lines and the one offset.
2. A 25% return fashion SKU vs 2% tools SKU - same policy OK?
3. When is refurbishing worth it over disposal?

<details>
<summary>Show answers</summary>

1. Return transport (in unit cost/processing), processing, disposal, admin - offset by resale value.

2. No - returns costs scale with rate; fashion needs stricter gatekeeping or better product info.

3. When resale value minus reprocessing beats the salvage from scrapping - compute it, don't guess it.

</details>

## Try this now

A $30 gadget has 10% returns, $5 processing, $2 disposal, $26 resale. Compute the net per-year cost on 10,000 units sold.

---
[← Warehouse Energy Consumption](energy_consumption_warehouse.md) · [Back to Sustainability library](README.md)

*New to this topic? Start with the core lesson first: [11_sustainability.md](../../modules/11_sustainability.md).*
