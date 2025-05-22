---
title: "Total Cost of Ownership (TCO) | supplycm Algorithm Library"
description: "Plain-English explanation of total_cost_of_ownership from the supplycm Supplier & Procurement module, with a runnable Python example and self-check questions."
keywords: "supplycm, supplier, total_cost_of_ownership, supply chain, plain english, supplier & procurement"
---

# Total Cost of Ownership (TCO)

> **Call it:** `from supplycm.supplier import total_cost_of_ownership` · **Level:** Intermediate · **You need:** basic arithmetic only

TCO adds up a purchase's whole life: price plus acquisition (freight, install), operating costs, downtime cost, and disposal. Two machines with the same sticker price can differ 40% over five years. TCO is how sourcing stops buying cheap and starts buying smart.

**Think of it like this:** Two puppies, same price - one eats more, visits the vet more, and chews the sofa. The cheap one was never cheap.

## When to reach for it

- Comparing equipment or suppliers with different running profiles
- Justifying a higher upfront price with lower lifetime cost

## Try it with supplycm

```python
from supplycm.supplier import total_cost_of_ownership

result = total_cost_of_ownership(purchase_price=50000, acquisition_cost=8000, operating_cost=12000, downtime_cost=5000, disposal_cost=2000)
print(result)
```

You should see something like:

```text
77000
```

77,000 total - the operating line alone exceeds the acquisition fee, which is exactly the line suppliers love to keep invisible.

## Check yourself

1. Which TCO line do buyers most often forget?
2. How does TCO change supplier conversations?
3. Over what horizon should you compute TCO?

<details>
<summary>Show answers</summary>

1. Downtime - an hour of stopped production can erase a year of unit-price savings.

2. It moves them from 'your price is 3% high' to 'your downtime cost is 40k' - specific, quantified, actionable.

3. The realistic ownership life - long enough to include operating and end-of-life, short enough that estimates stay honest.

</details>

## Try this now

TCO two forklifts over 5 years: A cheaper to buy, thirstier and slower; B the reverse. Crown the winner and the deciding line.

---
[← Supplier Segmentation (Kraljic)](supplier_segmentation.md) · [Back to Supplier & Procurement library](README.md) · [Should-Cost Analysis →](should_cost_analysis.md)

*New to this topic? Start with the core lesson first: [04_suppliers.md](../../modules/04_suppliers.md).*
