# Supply Chain Cheat Sheet

Quick reference for the most important formulas and concepts. All formulas use Python notation.

## Forecasting

| Method | Python Formula | When to Use |
|--------|---------------|-------------|
| Naive | `forecast = sales[-1]` | Simple baseline |
| Moving Average | `forecast = sum(last_n) / n` | Stable demand |
| Exponential Smoothing | `forecast = alpha * today + (1 - alpha) * yesterday` | Trending demand |
| Holt-Winters | (complex, uses supplycm) | Seasonal demand |
| Croston's | (uses supplycm) | Intermittent demand |

**Accuracy (MAPE):**

```python
error = abs(actual - forecast) / actual
mape = sum(all_errors) / count * 100
```

## Inventory

```python
# EOQ - Economic Order Quantity
eoq = (2 * annual_demand * ordering_cost / holding_cost) ** 0.5

# Safety Stock
import math
safety_stock = z_score * demand_std * (lead_time ** 0.5)

# Reorder Point
reorder_point = (demand_per_week * lead_time) + safety_stock

# Fill Rate
fill_rate = 1 - expected_shortage / order_quantity
```

**Z-scores:** `1.645` = 95% | `1.96` = 97.5% | `2.33` = 99%

**ABC Analysis:** A = 80% of value, B = 15%, C = 5%

## Suppliers

| Method | Purpose |
|--------|---------|
| AHP | Calculate criteria weights |
| TOPSIS | Rank suppliers |
| Kraljic Matrix | Classify suppliers by risk and profit |

**Kraljic Categories:**
- Strategic: high risk, high profit (partner)
- Leverage: low risk, high profit (negotiate)
- Bottleneck: high risk, low profit (secure)
- Routine: low risk, low profit (automate)

## Routing

| Problem | Solution |
|---------|----------|
| TSP (one vehicle) | Nearest neighbor, then 2-opt |
| VRP (multiple vehicles) | Clarke-Wright savings |
| Assignment | Hungarian algorithm |

## Quality

```python
# DPMO - Defects Per Million Opportunities
dpmo = (defects / (units * opportunities)) * 1_000_000

# Cp - Process Capability (potential)
cp = (upper_spec - lower_spec) / (6 * std_dev)

# Cpk - Process Capability (actual)
cp_upper = (upper_spec - mean) / (3 * std_dev)
cp_lower = (mean - lower_spec) / (3 * std_dev)
cpk = min(cp_upper, cp_lower)
```

**Targets:** DPMO = 3.4 for Six Sigma | Cp/Cpk >= 1.33 for capable process

## Lean

```python
# Takt Time
takt_time = available_time / customer_demand

# OEE - Overall Equipment Effectiveness
oee = availability * performance * quality

# Cycle Time Efficiency
efficiency = value_added_time / total_cycle_time

# WIP (Little's Law)
work_in_progress = throughput_rate * flow_time
```

**8 Wastes (DOWNTIME):** Defects, Overproduction, Waiting, Non-utilized talent, Transportation, Inventory, Motion, Excess processing

## S&OP

| Strategy | Description | Best For |
|----------|-------------|----------|
| Chase | Production matches demand | Perishable goods |
| Level | Constant production | Stable workforce |

## Contracts

| Contract | How It Works | When to Use |
|----------|-------------|-------------|
| Revenue Sharing | Lower wholesale + share of revenue | Align incentives |
| Buyback | Supplier buys unsold stock | Uncertain demand |
| Quantity Flexibility | Adjust order within range | Somewhat predictable |

## Sustainability

```python
# Carbon Footprint
co2_emissions = distance * weight * emission_factor

# Reverse Logistics Cost
cost = return_rate * (processing_cost + disposal_cost * (1 - resale_value / unit_cost))
```

**Emission Factors (kg CO2 per tonne-km):**
- Air: 0.602
- Truck: 0.062
- Train: 0.022
- Ship: 0.016

## Key Numbers to Remember

- Six Sigma = 3.4 DPMO
- World-class OEE = 85%
- Typical holding cost = 20-30% of item value per year
- ABC split: 80/15/5
- `z_score = 1.96` for 97.5% service level
- `takt_time = available_time / customer_demand`
- `work_in_progress = throughput_rate * flow_time` (Little's Law)
