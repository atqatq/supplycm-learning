---
title: "Revenue Sharing Contract | supplycm Algorithm Library"
description: "Plain-English explanation of revenue_sharing_contract from the supplycm Contracts module, with a runnable Python example and self-check questions."
keywords: "supplycm, contracts, revenue_sharing_contract, supply chain, plain english, contracts"
---

# Revenue Sharing Contract

> **Call it:** `from supplycm.contracts import revenue_sharing_contract` · **Level:** Intermediate · **You need:** basic arithmetic only

Instead of paying a high wholesale price, the buyer pays a lower price PLUS a share of the revenue it earns. The supplier earns less per unit sold but shares in the upside when sales boom. Done right, both sides end up better than under a plain wholesale deal.

**Think of it like this:** A landlord charging lower rent plus a small cut of your cafe's daily takings - you survive slow months, they share the good ones.

## When to reach for it

- Video-rental/blockbuster-style deals where demand risk is high
- Aligning supplier incentive with actual sales, not just orders placed

## Try it with supplycm

```python
from supplycm.contracts import revenue_sharing_contract

result = revenue_sharing_contract(wholesale_price=5.0, retail_price=10.0, revenue_share_fraction=0.3, demand=1000, unit_cost=3.0)
print(result)
```

You should see something like:

```text
{'supplier_profit': 5000.0, 'retailer_profit': 2000.0, 'total_profit': 7000.0}
```

The result dict shows each side's profit under the share deal - compare with a plain wholesale deal at a higher wholesale price to see who gains.

## Check yourself

1. What does the buyer give up in exchange for a lower wholesale price?
2. Why does revenue sharing reduce the buyer's overstock pain?
3. Name the classic industry for this contract.

<details>
<summary>Show answers</summary>

1. A slice of every sale's revenue - the supplier trades margin now for a stake in outcomes.

2. Less capital is tied per unit, so unsold stock hurts less - the buyer can afford more inventory.

3. Video rentals in the 1990s - studios took shares of rental revenue so stores could stock many copies.

</details>

## Try this now

Model demand 800 vs 1,400 with the same contract; explain how the share changes each side's risk.

---
[Back to Contracts library](README.md) · [Buyback Contract →](buyback_contract.md)

*New to this topic? Start with the core lesson first: [10_contracts.md](../../modules/10_contracts.md).*
