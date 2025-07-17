---
title: "Buyback Contract | supplycm Algorithm Library"
description: "Plain-English explanation of buyback_contract from the supplycm Contracts module, with a runnable Python example and self-check questions."
keywords: "supplycm, contracts, buyback_contract, supply chain, plain english, contracts"
---

# Buyback Contract

> **Call it:** `from supplycm.contracts import buyback_contract` · **Level:** Intermediate · **You need:** basic arithmetic only

The supplier promises to buy back unsold stock at a set price at season's end. The buyer dares to order more (stockouts drop), while the supplier gains bigger sales for taking on the leftover risk. Fashion and publishing use this constantly.

**Think of it like this:** A bookshop returning unsold newspapers to the publisher - the shop stocks boldly because leftovers aren't a total loss.

## When to reach for it

- Short-life products with uncertain demand (fashion, books, media)
- Fixing a supply chain where the retailer under-orders out of fear

## Try it with supplycm

```python
from supplycm.contracts import buyback_contract

result = buyback_contract(wholesale_price=6.0, retail_price=12.0, buyback_price=3.0, demand=1200, unit_cost=4.0)
print(result)
```

You should see something like:

```text
{'supplier_profit': 2400.0, 'retailer_profit': 7200.0, 'total_profit': 9600.0}
```

The dict reports both profits under the buyback - the buyer orders more because leftovers recover 3.0 each instead of 0.

## Check yourself

1. Who takes on the leftover risk under a buyback?
2. Why do total supply chain profits often rise?
3. What happens if the buyback price is set too high?

<details>
<summary>Show answers</summary>

1. The supplier - it pays for returns, which is why it can afford the higher wholesale price it charges.

2. The buyer orders closer to the true demand, so fewer sales are lost to empty shelves.

3. The buyer over-orders carelessly - returns pile up and the supplier's margin evaporates.

</details>

## Try this now

Compare buyer profit with buyback price 0 vs 3.0 at the same demand; explain why the buyer orders more in the second.

---
[← Revenue Sharing Contract](revenue_sharing_contract.md) · [Back to Contracts library](README.md) · [Quantity Flexibility Contract →](quantity_flexibility_contract.md)

*New to this topic? Start with the core lesson first: [10_contracts.md](../../modules/10_contracts.md).*
