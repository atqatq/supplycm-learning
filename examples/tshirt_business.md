---
title: "T-Shirt Business Supply Chain | Procurement and Contracts"
description: "Supply chain example for a t-shirt printing business. Learn bulk purchasing, supplier contracts, and sustainability."
keywords: "t-shirt business, apparel supply chain, procurement, buyback contract, sustainable fashion, screen printing"
---

# Example: T-Shirt Business

## The Business

A small t-shirt printing business.

## Key Decisions

### 1. Inventory

```python
from supplycm.inventory import economic_order_quantity

# Buy blank shirts in bulk
eoq = economic_order_quantity(5000, 30, 4)
print(f"Order {eoq:.0f} blank shirts at a time")
```

### 2. Supplier

```python
from supplycm.supplier import topsis

# Compare 3 shirt suppliers
ranking = topsis(
    [[80, 90, 85], [90, 75, 80], [70, 95, 90]],
    [0.4, 0.35, 0.25],
    ['benefit', 'benefit', 'benefit']
)
print(f"Best supplier: #{ranking[0]+1}")
```

### 3. Contracts

```python
from supplycm.contracts import buyback_contract

# If shirts do not sell, supplier buys back
result = buyback_contract(5, 15, 3, 800, 2, 1)
print(f"Supplier profit: ${result['supplier_profit']}")
print(f"Your profit: ${result['retailer_profit']}")
```

### 4. Sustainability

```python
from supplycm.sustainability import carbon_footprint_transport

# Shirts shipped 1000 km by truck, 500 kg = 0.5 tonnes
co2 = carbon_footprint_transport(1000, 0.5)
print(f"CO2 per shipment: {co2:.0f} kg")
```

## Key Insights

- Buy blanks in bulk (EOQ)
- Choose supplier carefully (quality matters for printing)
- Negotiate buyback for unsold inventory
- Consider environmental impact of shipping
