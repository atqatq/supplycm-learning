---
title: "Landed Cost | supplycm Algorithm Library"
description: "Plain-English explanation of landed_cost from the supplycm Costing module, with a runnable Python example and self-check questions."
keywords: "supplycm, cost, landed_cost, supply chain, plain english, costing"
---

# Landed Cost

> **Call it:** `from supplycm.cost import landed_cost` · **Level:** Beginner · **You need:** basic arithmetic only

Landed cost is what a product REALLY costs to get to your door: unit price plus freight, duty, insurance, handling, and broker fees, optionally per unit. A 'cheap' part from far away often loses to a pricier local one once everything is added. This function does that addition honestly.

**Think of it like this:** Ticket price vs the real cost of the trip: baggage, transfer, hotel shuttle - the price tag is only the start.

## When to reach for it

- Comparing overseas vs local suppliers on equal footing
- Deciding whether a price increase is actually an increase after duty changes

## Try it with supplycm

```python
from supplycm.cost import landed_cost

result = landed_cost(unit_price=10.0, freight=1500.0, duty_rate=0.05, insurance_rate=0.01, handling=200.0, customs_broker=100.0, quantity=1000)
print(result)
```

You should see something like:

```text
12.4
```

About 11.95 per unit landed - almost 20% above the sticker price; that is the number to use in sourcing decisions.

> **Watch out:** Quote and compare suppliers in LANDED cost per unit - never in sticker price.

## Check yourself

1. Why is sticker price a lie in global sourcing?
2. Duty rate rises from 5% to 12% on a cheap import. What lands on your desk?
3. Name two often-forgotten cost lines in imports.

<details>
<summary>Show answers</summary>

1. Freight, duty, insurance, and handling can add 10-30% - the landed number is what hits your books.

2. A new landed cost per unit - often flipping the decision toward the 'expensive' local supplier.

3. Customs broker fees and insurance - small individually, real in total.

</details>

## Try this now

Compute landed cost for a $5 part shipped 5,000 units with $2,000 freight and 8% duty; then find the break-even local price.

---
[Back to Costing library](README.md) · [Total Procurement Cost →](total_cost_procurement.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
