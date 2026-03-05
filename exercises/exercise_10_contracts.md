# Exercise 10: Contracts

## Problem

You are a retailer. Supplier cost is $20 per unit. You sell for $60. Demand is 1000 units.

Compare three contracts:

1. **Standard**: Buy at $35, sell at $60
2. **Revenue sharing**: Buy at $25, share 20% of revenue
3. **Buyback**: Buy at $40, supplier buys back unsold at $20

### Tasks

Calculate profits for both parties under each contract. Which is best?

## Your Answer

| Contract | Supplier Profit | Retailer Profit | Total |
|----------|----------------|-----------------|-------|
| Standard | ___ | ___ | ___ |
| Revenue sharing | ___ | ___ | ___ |
| Buyback | ___ | ___ | ___ |

---

<details>
<summary>Click to reveal answers</summary>

### Using supplycm

```python
from supplycm.contracts import revenue_sharing_contract, buyback_contract

# 1. Standard
supplier_standard = (35 - 20) * 1000
retailer_standard = (60 - 35) * 1000
print(f"Standard: Supplier=${supplier_standard}, Retailer=${retailer_standard}, Total=${supplier_standard + retailer_standard}")

# 2. Revenue sharing
rs = revenue_sharing_contract(25, 60, 0.20, 1000, 20)
print(f"Revenue sharing: Supplier=${rs['supplier_profit']}, Retailer=${rs['retailer_profit']}, Total=${rs['total_profit']}")

# 3. Buyback (assume 800 sold, 200 unsold)
bb = buyback_contract(40, 60, 20, 800, 20, 10)
print(f"Buyback: Supplier=${bb['supplier_profit']}, Retailer=${bb['retailer_profit']}, Total=${bb['total_profit']}")
```

</details>
