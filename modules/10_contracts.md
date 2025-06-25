# Module 10: Making Deals (Contracts)

## The Big Idea

A contract is an agreement between a buyer and a supplier. The right contract aligns incentives so both parties benefit.

## Why Does It Matter?

Bad contracts cause problems:

- Supplier and buyer fight over who bears risk
- One party might act selfishly, hurting the other
- Total profit is lower than it could be

Good contracts make both parties want to cooperate, increasing total profit.

## The Problem: Double Marginalization

If both the supplier and the retailer add their own profit margin, the final price is too high. Customers buy less. Both parties make less money than if they cooperated.

This is called double marginalization.

### Example

- Supplier cost: $20
- Supplier sells to retailer for: $40 (margin = $20)
- Retailer sells to customer for: $80 (margin = $40)
- Customer thinks $80 is too expensive, buys less

If supplier and retailer cooperated, they could lower the price, sell more, and both make more money.

## Types of Contracts

### 1. Revenue Sharing Contract

The supplier charges a lower wholesale price, but gets a share of the retailer's sales revenue.

**How it works:**
- Supplier sells to retailer for $30 (instead of $40)
- Retailer sells to customer for $70
- Retailer gives supplier 20% of revenue ($14 per unit)
- Supplier total: $30 + $14 = $44 (more than before)
- Retailer total: $70 - $30 - $14 = $26

Both parties want high sales, so they cooperate.

### Try it with supplycm

```python
from supplycm.contracts import revenue_sharing_contract

result = revenue_sharing_contract(
    wholesale_price=30,
    retail_price=70,
    revenue_share_fraction=0.2,
    demand=1000,
    unit_cost=20
)
print(f"Supplier profit: ${result['supplier_profit']}")
print(f"Retailer profit: ${result['retailer_profit']}")
print(f"Total profit: ${result['total_profit']}")
```

### 2. Buyback Contract

The supplier agrees to buy back unsold inventory at a set price. This reduces the retailer's risk.

**How it works:**
- Supplier sells to retailer for $40
- Retailer orders 1000 units
- If only 800 sell, supplier buys back 200 at $25 each
- Retailer's risk is lower, so they order more

### Try it with supplycm

```python
from supplycm.contracts import buyback_contract

result = buyback_contract(
    wholesale_price=40,
    retail_price=80,
    buyback_price=25,
    demand=800,
    unit_cost=20,
    salvage_value=10
)
print(f"Supplier profit: ${result['supplier_profit']}")
print(f"Retailer profit: ${result['retailer_profit']}")
```

### 3. Quantity Flexibility Contract

The retailer can adjust their order within a range. Useful when demand is uncertain.

**How it works:**
- Retailer orders 1000 units
- Contract allows +/- 20% adjustment
- Actual demand is 900
- Retailer orders 900 (within the range)

### Try it with supplycm

```python
from supplycm.contracts import quantity_flexibility_contract

result = quantity_flexibility_contract(
    wholesale_price=40,
    retail_price=80,
    order_quantity=1000,
    actual_demand=900,
    unit_cost=20,
    flexibility_fraction=0.2
)
print(f"Final quantity: {result['final_quantity']}")
print(f"Supplier profit: ${result['supplier_profit']}")
```

## Choosing the Right Contract

| Situation | Recommended Contract |
|-----------|---------------------|
| Retailer has low cash flow | Revenue sharing |
| Demand is very uncertain | Buyback |
| Demand is somewhat predictable | Quantity flexibility |
| Simple, stable relationship | Standard wholesale |

## Quick Quiz

1. What is double marginalization?
2. How does a revenue sharing contract work?
3. Why would a supplier agree to a buyback contract?
4. When would you use a quantity flexibility contract?

<details>
<summary>Click to reveal answers</summary>

1. When both supplier and retailer add their own margin, the price is too high and total profit is lower
2. Supplier charges lower wholesale price but gets a percentage of sales
3. To encourage the retailer to order more (less risk for retailer means more sales for supplier)
4. When demand is uncertain but somewhat predictable

</details>

## Exercise

You are a retailer buying toys from a supplier.

1. Supplier cost: $10 per toy
2. You sell toys for $30 each
3. Demand is uncertain: could be 500 or 1000

Compare three contracts:
- Standard: buy at $20, sell at $30
- Revenue sharing: buy at $12, share 30% of revenue
- Buyback: buy at $20, supplier buys back unsold at $10

Which contract do you prefer? Why?

## Key Words

- **Contract**: An agreement between buyer and supplier
- **Double marginalization**: When both parties add margins, price is too high
- **Revenue sharing**: Supplier gets a cut of sales
- **Buyback**: Supplier buys back unsold inventory
- **Quantity flexibility**: Retailer can adjust order within a range

## What's Next?

Now you know how to make deals. But what about the environment? The next lesson is about sustainability.

Next: [Module 11 - Being Green (Sustainability)](11_sustainability.md)
