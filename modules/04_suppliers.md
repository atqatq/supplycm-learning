# Module 4: Working with Suppliers

## The Big Idea

A supplier is a company that sells you the materials or products you need. Choosing good suppliers and managing them well is a big part of supply chain management.

## Why Does It Matter?

A bad supplier can ruin your business:

- Late deliveries mean you cannot make your product on time
- Poor quality materials mean your product is bad
- High prices mean you cannot compete

A good supplier is like a partner. They help you succeed.

## How to Choose a Supplier

When picking a supplier, think about more than just price. Consider:

1. **Price**: Are they affordable?
2. **Quality**: Is their stuff good?
3. **Delivery**: Do they deliver on time?
4. **Reliability**: Can you count on them?
5. **Service**: Do they help when there is a problem?

## A Method for Choosing: AHP

AHP stands for Analytic Hierarchy Process. It helps you make decisions when many things matter.

Here is how it works:

1. List your criteria (price, quality, delivery, etc.)
2. Compare them in pairs: "Is price more important than quality? By how much?"
3. AHP turns your answers into weights (numbers that show importance)
4. Score each supplier on each criterion
5. Multiply scores by weights and add up

### Try it with supplycm

```python
from supplycm.supplier import ahp_supplier_selection

# Compare 3 criteria: Price, Quality, Delivery
# 1 = equal, 3 = slightly more important, 5 = much more important
pairwise = [
    [1,     3,   5],   # Price vs Quality, Price vs Delivery
    [1/3,   1,   3],   # Quality vs Price, Quality vs Delivery
    [1/5, 1/3,   1],   # Delivery vs Price, Delivery vs Quality
]

weights = ahp_supplier_selection(pairwise)
print(f"Price weight: {weights[0]:.2f}")
print(f"Quality weight: {weights[1]:.2f}")
print(f"Delivery weight: {weights[2]:.2f}")
# Price is most important here
```

## Ranking Suppliers: TOPSIS

Once you have weights, you can rank suppliers using TOPSIS.

TOPSIS works like this:

1. Score each supplier on each criterion
2. Find the "best possible" supplier (highest scores everywhere)
3. Find the "worst possible" supplier (lowest scores everywhere)
4. Rank suppliers by how close they are to the best

### Try it with supplycm

```python
from supplycm.supplier import topsis

# 3 suppliers, scored on Price (low=good), Quality, Delivery
# Higher score = better (we will use benefit for all here)
decision_matrix = [
    [80, 90, 85],  # Supplier A
    [70, 85, 90],  # Supplier B
    [85, 80, 70],  # Supplier C
]

weights = [0.5, 0.3, 0.2]  # from AHP
criteria_type = ['benefit', 'benefit', 'benefit']  # higher is better

ranking = topsis(decision_matrix, weights, criteria_type)
print(f"Best supplier is number {ranking[0] + 1}")
```

## Sorting Suppliers: Kraljic Matrix

Not all suppliers are equally important. The Kraljic Matrix sorts them into 4 groups:

### 1. Strategic (high risk, high profit)
These are your most important suppliers. Build close partnerships.

Example: The company that makes the engine for your cars.

### 2. Leverage (low risk, high profit)
These suppliers are easy to find but important. Negotiate hard for the best deal.

Example: The company that supplies packaging materials.

### 3. Bottleneck (high risk, low profit)
These are hard to find but not very valuable. Secure your supply.

Example: A rare component only one company makes.

### 4. Routine (low risk, low profit)
These are common and not very valuable. Buy them simply.

Example: Office supplies.

### Try it with supplycm

```python
from supplycm.supplier import supplier_segmentation

suppliers = [
    ('Engine Maker', 0.9, 0.8),   # high profit, high risk
    ('Box Supplier', 0.7, 0.2),   # high profit, low risk
    ('Rare Parts', 0.2, 0.9),     # low profit, high risk
    ('Office Store', 0.3, 0.3),   # low profit, low risk
]

result = supplier_segmentation(suppliers)
for name, group in result:
    print(f"{name}: {group}")
```

## Measuring Supplier Performance

Once you pick a supplier, you need to check if they are doing a good job. Common metrics:

- **On-time delivery rate**: What percentage of deliveries arrive on time?
- **Defect rate**: What percentage of products are bad?
- **Cost performance**: Are they keeping prices competitive?

### Try it with supplycm

```python
from supplycm.supplier import on_time_delivery_rate

deliveries = [
    (10, 9),   # due day 10, arrived day 9 (early)
    (15, 15),  # due day 15, arrived day 15 (on time)
    (20, 22),  # due day 20, arrived day 22 (late)
]

rate = on_time_delivery_rate(deliveries)
print(f"On-time delivery rate: {rate*100:.1f}%")
# 2 out of 3 = 66.7%
```

## Quick Quiz

1. What does AHP stand for?
2. In the Kraljic Matrix, which type of supplier needs the closest partnership?
3. If a supplier delivers 8 out of 10 orders on time, what is the on-time delivery rate?
4. Why should you consider more than just price when choosing a supplier?

<details>
<summary>Click to reveal answers</summary>

1. Analytic Hierarchy Process
2. Strategic suppliers (high risk, high profit)
3. 80%
4. Because quality, delivery, and reliability also matter

</details>

## Exercise

You need to pick a supplier for t-shirts. You have 3 options:

| Supplier | Price Score | Quality Score | Delivery Score |
|----------|-------------|---------------|----------------|
| A | 70 | 90 | 80 |
| B | 90 | 70 | 75 |
| C | 80 | 80 | 90 |

1. Use AHP to decide weights for Price, Quality, Delivery (what matters most to you?)
2. Use TOPSIS to rank the suppliers
3. Which supplier would you pick? Why?

## Key Words

- **Supplier**: A company that provides materials or products
- **AHP**: A method for making decisions with multiple criteria
- **TOPSIS**: A method for ranking options
- **Kraljic Matrix**: A tool for sorting suppliers by risk and profit
- **On-time delivery rate**: Percentage of deliveries that arrive on time

## What's Next?

Now you have your stuff. Where do you put it? The next lesson is about warehouses.

Next: [Module 5 - Storing Stuff (Warehouses)](05_warehouses.md)
