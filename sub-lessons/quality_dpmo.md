# Understanding DPMO

## What is DPMO?

DPMO stands for Defects Per Million Opportunities. It tells you how many defects you would have if you made a million products.

## The Formula in Python

```python
dpmo = (defects / (units * opportunities)) * 1_000_000
```

Where:
- `defects` = number of bad things found
- `units` = number of products made
- `opportunities` = number of ways each product can be bad

## Step by Step Example

### The Situation

You make 1000 toys. Each toy has 10 things that could go wrong (10 opportunities). You found 50 defects.

### Step 1: Count Total Opportunities

```python
units = 1000
opportunities_per_unit = 10

total_opportunities = units * opportunities_per_unit
# = 1000 * 10
# = 10,000

print(f'Total opportunities: {total_opportunities}')
```

### Step 2: Calculate Defect Rate

```python
defects = 50

defect_rate = defects / total_opportunities
# = 50 / 10,000
# = 0.005 (0.5%)

print(f'Defect rate: {defect_rate * 100:.2f}%')
```

### Step 3: Convert to Per Million

```python
dpmo = defect_rate * 1_000_000
# = 0.005 * 1,000,000
# = 5,000

print(f'DPMO: {dpmo}')
```

This means: if you made a million toys (with 10 checks each), you would have about 5,000 defects.

### Try it with supplycm

```python
from supplycm.quality import dpmo, sigma_level

dpmo_value = dpmo(50, 1000, 10)
sigma = sigma_level(dpmo_value)

print(f'DPMO: {dpmo_value}')
print(f'Sigma level: {sigma}')
```

## Sigma Levels

| DPMO | Sigma Level | Quality |
|------|-------------|---------|
| 3.4 | 6.0 | Six Sigma (world class) |
| 233 | 5.0 | Excellent |
| 6,210 | 4.0 | Good |
| 66,807 | 3.0 | Average |
| 158,655 | 2.5 | Below average |
| 308,537 | 2.0 | Poor |
| 500,000 | 1.5 | Very poor |
| 691,462 | 1.0 | Bad |

## Another Example

```python
# A bakery makes 500 cookies
# Each cookie has 5 things that could go wrong
# They found 10 defects

units = 500
opportunities = 5
defects = 10

dpmo_value = dpmo(defects, units, opportunities)
sigma = sigma_level(dpmo_value)

print(f'Cookies made: {units}')
print(f'Opportunities per cookie: {opportunities}')
print(f'Defects found: {defects}')
print(f'DPMO: {dpmo_value:.0f}')
print(f'Sigma level: {sigma:.1f}')
```

## Key Takeaway

DPMO lets you compare quality across different products and processes. It answers: "If I made a million of these, how many would be bad?"

```python
dpmo = (defects / (units * opportunities)) * 1_000_000
```
