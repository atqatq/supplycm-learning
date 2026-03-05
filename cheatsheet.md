# Supply Chain Cheat Sheet

Quick reference for the most important formulas and concepts.

## Forecasting

| Method | Formula | When to Use |
|--------|---------|-------------|
| Naive | F(t+1) = X(t) | Simple baseline |
| Moving Average | F = (X1 + X2 + ... + Xn) / n | Stable demand |
| Exponential Smoothing | F(t+1) = alpha * X(t) + (1-alpha) * F(t) | Trending demand |
| Holt-Winters | Complex (trend + seasonality) | Seasonal demand |
| Croston's | Separate demand size and interval | Intermittent demand |

**Accuracy:** MAPE = average of |Actual - Forecast| / |Actual| x 100

## Inventory

| Formula | Calculation |
|---------|-------------|
| EOQ | sqrt(2 * D * S / H) |
| Safety Stock | Z * sigma * sqrt(L) |
| Reorder Point | (d * L) + SS |
| Fill Rate | 1 - E(shortage) / Q |

**Z-scores:** 1.645 = 95% | 1.96 = 97.5% | 2.33 = 99%

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

| Metric | Formula | Target |
|--------|---------|--------|
| DPMO | (defects / (units * opportunities)) * 1M | 3.4 for Six Sigma |
| Cp | (USL - LSL) / (6 * sigma) | >= 1.33 |
| Cpk | min((USL-mean), (mean-LSL)) / (3*sigma) | >= 1.33 |
| Sigma Level | From DPMO table | 6.0 for Six Sigma |

## Lean

| Metric | Formula | Target |
|--------|---------|--------|
| Takt Time | Available Time / Demand | Match production pace |
| OEE | Availability * Performance * Quality | >= 85% |
| Cycle Efficiency | Value-Added / Total Time | >= 50% |
| WIP (Little's Law) | Throughput * Flow Time | Minimize |

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

| Formula | Calculation |
|---------|-------------|
| Carbon Footprint | distance * weight * emission factor |
| Reverse Logistics Cost | return_rate * (processing + disposal - resale) |

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
- Z = 1.96 for 97.5% service level
- Takt time = available time / demand
- WIP = throughput * flow time (Little's Law)
