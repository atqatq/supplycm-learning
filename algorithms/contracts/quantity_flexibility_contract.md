---
title: "Quantity Flexibility Contract | supplycm Algorithm Library"
description: "Plain-English explanation of quantity_flexibility_contract from the supplycm Contracts module, with a runnable Python example and self-check questions."
keywords: "supplycm, contracts, quantity_flexibility_contract, supply chain, plain english, contracts"
---

# Quantity Flexibility Contract

> **Call it:** `from supplycm.contracts import quantity_flexibility_contract` · **Level:** Intermediate · **You need:** basic arithmetic only

The buyer may adjust its order up or down by an agreed fraction after seeing early demand - say, plus or minus 20%. Forecasts improve near the season, so both sides benefit from the correction window without any cash changing hands for leftovers.

**Think of it like this:** Pre-ordering 100 pizzas for a party but being allowed to change to 80-120 once you see who actually shows up.

## When to reach for it

- Long lead times that force early, uncertain commitments
- Electronics and fashion with demand signals emerging close to season

## Try it with supplycm

```python
from supplycm.contracts import quantity_flexibility_contract

result = quantity_flexibility_contract(wholesale_price=6.0, retail_price=12.0, order_quantity=1000, actual_demand=850, unit_cost=4.0, flexibility_fraction=0.2)
print(result)
```

You should see something like:

```text
{'final_quantity': 850, 'supplier_profit': 1700.0, 'retailer_profit': 5100.0, 'total_profit': 6800.0}
```

The dict shows the adjusted order and each side's profit - the buyer trims toward 850 within the 20% band instead of eating 150 unsold units.

## Check yourself

1. What can the buyer change under this contract?
2. Why does the supplier accept flexibility?
3. Flexibility 5% vs 30% - trade-off?

<details>
<summary>Show answers</summary>

1. The order size, within a band (e.g., 20% below to 20% above the original commitment).

2. It charges for the option (usually a higher wholesale price) and gains a committed base order.

3. 5% barely helps the buyer; 30% protects them but the supplier prices that risk in - the sweet spot is negotiated, not maximal.

</details>

## Try this now

With order 1,000 and flexibility 0.2, what order can the buyer place if demand lands at 750? Compute profits for both sides.

---
[← Buyback Contract](buyback_contract.md) · [Back to Contracts library](README.md)

*New to this topic? Start with the core lesson first: [10_contracts.md](../../modules/10_contracts.md).*
