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

## Every Algorithm at a Glance

The full library - all 396 algorithms, one line each. Detailed pages live in the [algorithm library](algorithms/README.md).

### Statistics & Accuracy (40)

```python
from supplycm.statistics import descriptive_stats
from supplycm.statistics import zscore
from supplycm.statistics import coefficient_of_variation
from supplycm.statistics import minmax_scale
from supplycm.statistics import outlier_detection_iqr
from supplycm.statistics import skewness
from supplycm.statistics import kurtosis
from supplycm.statistics import correlation
from supplycm.statistics import spearman_correlation
from supplycm.statistics import r_squared
from supplycm.statistics import coefficient_of_determination
from supplycm.statistics import adjusted_r_squared
from supplycm.statistics import confidence_interval_mean
from supplycm.statistics import bootstrap_confidence_interval
from supplycm.statistics import moving_average_smooth
from supplycm.statistics import exponential_smooth
from supplycm.statistics import anova_one_way
from supplycm.statistics import f_test_variance
from supplycm.statistics import t_test_one_sample
from supplycm.statistics import t_test_two_sample
from supplycm.statistics import tracking_signal_threshold
from supplycm.statistics import bias
from supplycm.statistics import mae
from supplycm.statistics import mse
from supplycm.statistics import rmse
from supplycm.statistics import mape
from supplycm.statistics import smape
from supplycm.statistics import mean_percentage_error
from supplycm.statistics import percent_bias
from supplycm.statistics import mase
from supplycm.statistics import forecast_value_added
from supplycm.statistics import diebold_mariano_test
from supplycm.statistics import anderson_darling_test
from supplycm.statistics import shapiro_wilk_approx
from supplycm.statistics import jarque_bera_test
from supplycm.statistics import chi_square_goodness_of_fit
from supplycm.statistics import kolmogorov_smirnov_test
from supplycm.statistics import kolmogorov_smirnov_two_sample
from supplycm.statistics import mann_whitney_u
from supplycm.statistics import wilcoxon_signed_rank
```

### Demand Planning (9)

```python
from supplycm.demand import demand_aggregation
from supplycm.demand import demand_disaggregation
from supplycm.demand import seasonality_index
from supplycm.demand import promotional_demand_lift
from supplycm.demand import cannibalization_effect
from supplycm.demand import stockout_demand_loss
from supplycm.demand import demand_sensing
from supplycm.demand import demand_class_abc_xyz
from supplycm.demand import trend_seasonal_decomposition_forecast
```

### Lean (4)

```python
from supplycm.lean import takt_time
from supplycm.lean import oee
from supplycm.lean import cycle_time_efficiency
from supplycm.lean import wip_calculation
```

### Quality (7)

```python
from supplycm.quality import dpmo
from supplycm.quality import sigma_level
from supplycm.quality import process_capability_cp
from supplycm.quality import process_capability_cpk
from supplycm.quality import x_bar_chart
from supplycm.quality import r_chart
from supplycm.quality import p_chart
```

### S&OP (3)

```python
from supplycm.sop import demand_supply_match
from supplycm.sop import production_chase_strategy
from supplycm.sop import production_level_strategy
```

### Simulation (2)

```python
from supplycm.simulation import monte_carlo_inventory
from supplycm.simulation import monte_carlo_risk
```

### Risk (1)

```python
from supplycm.risk import supply_chain_resilience_index
```

### Costing (2)

```python
from supplycm.cost import landed_cost
from supplycm.cost import total_cost_procurement
```

### Sustainability (3)

```python
from supplycm.sustainability import carbon_footprint_transport
from supplycm.sustainability import energy_consumption_warehouse
from supplycm.sustainability import reverse_logistics_cost
```

### Contracts (3)

```python
from supplycm.contracts import revenue_sharing_contract
from supplycm.contracts import buyback_contract
from supplycm.contracts import quantity_flexibility_contract
```

### Supplier & Procurement (30)

```python
from supplycm.supplier import weighted_point_method
from supplycm.supplier import supplier_evaluation_matrix
from supplycm.supplier import vendor_scorecard
from supplycm.supplier import on_time_delivery_rate
from supplycm.supplier import lead_time_quoted_vs_actual
from supplycm.supplier import purchase_order_compliance
from supplycm.supplier import price_analysis
from supplycm.supplier import purchase_price_variance
from supplycm.supplier import spend_analysis
from supplycm.supplier import maverick_spend_detection
from supplycm.supplier import supplier_consolidation
from supplycm.supplier import supplier_diversity_index
from supplycm.supplier import negotiation_zone
from supplycm.supplier import competitive_bidding
from supplycm.supplier import contract_compliance_score
from supplycm.supplier import supplier_audit_score
from supplycm.supplier import supplier_rating
from supplycm.supplier import supplier_risk_score
from supplycm.supplier import preferred_supplier_index
from supplycm.supplier import supplier_segmentation
from supplycm.supplier import total_cost_of_ownership
from supplycm.supplier import should_cost_analysis
from supplycm.supplier import ahp_supplier_selection
from supplycm.supplier import analytic_network_process
from supplycm.supplier import topsis
from supplycm.supplier import fuzzy_topsis
from supplycm.supplier import promethee
from supplycm.supplier import electre
from supplycm.supplier import data_envelopment_analysis
from supplycm.supplier import strategic_supplier_scorecard
```

### Warehouse (10)

```python
from supplycm.warehouse import warehouse_slotting_abc
from supplycm.warehouse import warehouse_layout_optimization
from supplycm.warehouse import putaway_strategy
from supplycm.warehouse import order_picking_wave
from supplycm.warehouse import s_shape_routing
from supplycm.warehouse import return_routing
from supplycm.warehouse import traveling_salesman_picking
from supplycm.warehouse import pallet_building
from supplycm.warehouse import dock_door_assignment
from supplycm.warehouse import cross_dock_scheduling
```

### MRP & Production Planning (30)

```python
from supplycm.mrp import bom_explosion
from supplycm.mrp import low_level_coding
from supplycm.mrp import where_used_query
from supplycm.mrp import modular_bom
from supplycm.mrp import planning_bom
from supplycm.mrp import shrinkage_factor
from supplycm.mrp import safety_lead_time
from supplycm.mrp import lead_time_offsetting
from supplycm.mrp import backflush
from supplycm.mrp import mrp_calculation
from supplycm.mrp import master_production_schedule
from supplycm.mrp import available_to_promise
from supplycm.mrp import capable_to_promise
from supplycm.mrp import lot_size_rule_l4l
from supplycm.mrp import lot_size_rule_foq
from supplycm.mrp import lot_size_rule_poq
from supplycm.mrp import lot_size_rule_epr
from supplycm.mrp import minimum_order_quantity
from supplycm.mrp import maximum_order_quantity
from supplycm.mrp import order_multiples
from supplycm.mrp import quantity_discount_mrp
from supplycm.mrp import capacity_requirements_planning
from supplycm.mrp import demand_time_fence
from supplycm.mrp import planning_time_fence
from supplycm.mrp import pegging
from supplycm.mrp import phantom_bom_handling
from supplycm.mrp import cycle_counting
from supplycm.mrp import rough_cut_capacity_planning
from supplycm.mrp import drum_buffer_rope
from supplycm.mrp import kaban_sizing
```

### Inventory (60)

```python
from supplycm.inventory import economic_order_quantity
from supplycm.inventory import inventory_carrying_rate
from supplycm.inventory import holding_cost_calculation
from supplycm.inventory import economic_production_quantity
from supplycm.inventory import eoq_with_backorders
from supplycm.inventory import eoq_quantity_discount
from supplycm.inventory import reorder_point
from supplycm.inventory import safety_stock_normal
from supplycm.inventory import safety_stock_with_lead_time_var
from supplycm.inventory import demand_during_lead_time
from supplycm.inventory import cycle_service_level
from supplycm.inventory import fill_rate_calculation
from supplycm.inventory import expected_backorder
from supplycm.inventory import expected_on_hand
from supplycm.inventory import stockout_cost
from supplycm.inventory import abc_analysis
from supplycm.inventory import xyz_analysis
from supplycm.inventory import abc_xyz_matrix
from supplycm.inventory import inventory_position
from supplycm.inventory import days_of_supply
from supplycm.inventory import inventory_turnover_ratio
from supplycm.inventory import inventory_to_sales_ratio
from supplycm.inventory import gmroi
from supplycm.inventory import aging_schedule
from supplycm.inventory import dead_stock_identification
from supplycm.inventory import slow_moving_detection
from supplycm.inventory import obsolescence_cost
from supplycm.inventory import fifo_valuation
from supplycm.inventory import lifo_valuation
from supplycm.inventory import weighted_average_cost
from supplycm.inventory import square_root_law
from supplycm.inventory import risk_pooling
from supplycm.inventory import bullwhip_effect
from supplycm.inventory import pipeline_inventory
from supplycm.inventory import anticipation_inventory
from supplycm.inventory import decoupling_inventory
from supplycm.inventory import newsvendor_model
from supplycm.inventory import marginal_analysis_newsvendor
from supplycm.inventory import optimal_stockout_probability
from supplycm.inventory import perishable_inventory
from supplycm.inventory import lot_for_lot
from supplycm.inventory import silver_meal
from supplycm.inventory import least_unit_cost
from supplycm.inventory import least_period_cost
from supplycm.inventory import part_period_balancing
from supplycm.inventory import periodic_order_quantity
from supplycm.inventory import wagner_whitin
from supplycm.inventory import fixed_order_quantity
from supplycm.inventory import periodic_review_policy
from supplycm.inventory import r_q_policy
from supplycm.inventory import s_s_policy
from supplycm.inventory import base_stock_policy
from supplycm.inventory import joint_replenishment
from supplycm.inventory import multi_echelon_inventory
from supplycm.inventory import vendor_managed_inventory
from supplycm.inventory import ordering_cost_allocation
from supplycm.inventory import spare_parts_fsn
from supplycm.inventory import spare_parts_ved
from supplycm.inventory import spare_parts_hml
from supplycm.inventory import spare_parts_sde
```

### Forecasting (50)

```python
from supplycm.forecasting import naive_forecast
from supplycm.forecasting import seasonal_naive_forecast
from supplycm.forecasting import average_method
from supplycm.forecasting import simple_moving_average
from supplycm.forecasting import weighted_moving_average
from supplycm.forecasting import rolling_mean_forecast
from supplycm.forecasting import moving_median_filter
from supplycm.forecasting import drift_method
from supplycm.forecasting import single_exponential_smoothing
from supplycm.forecasting import ses_with_drift
from supplycm.forecasting import holt_linear_trend
from supplycm.forecasting import dampened_trend
from supplycm.forecasting import holt_winters
from supplycm.forecasting import doubling_seasonal_smoothing
from supplycm.forecasting import classical_decomposition
from supplycm.forecasting import mstl_decomposition
from supplycm.forecasting import seasonal_trend_loess
from supplycm.forecasting import seasonal_indices
from supplycm.forecasting import crostons_method
from supplycm.forecasting import croston_with_decay
from supplycm.forecasting import sba_method
from supplycm.forecasting import tsb_method
from supplycm.forecasting import pegels_classification
from supplycm.forecasting import linear_regression_forecast
from supplycm.forecasting import polynomial_regression_forecast
from supplycm.forecasting import exponential_trend_forecast
from supplycm.forecasting import gompertz_trend
from supplycm.forecasting import logistic_trend
from supplycm.forecasting import browns_double_exponential
from supplycm.forecasting import browns_triple_exponential
from supplycm.forecasting import theta_method
from supplycm.forecasting import ar_model
from supplycm.forecasting import ma_model
from supplycm.forecasting import var_model
from supplycm.forecasting import autocorrelation
from supplycm.forecasting import partial_autocorrelation
from supplycm.forecasting import ljung_box_test
from supplycm.forecasting import adf_test
from supplycm.forecasting import kpss_test
from supplycm.forecasting import hurst_exponent
from supplycm.forecasting import theils_u
from supplycm.forecasting import box_cox_transform
from supplycm.forecasting import inverse_box_cox
from supplycm.forecasting import akaike_information_criterion
from supplycm.forecasting import bayesian_information_criterion
from supplycm.forecasting import bates_granger_combination
from supplycm.forecasting import top_down_reconciliation
from supplycm.forecasting import bottom_up_reconciliation
from supplycm.forecasting import tracking_signal
from supplycm.forecasting import brier_score
```

### Scheduling (40)

```python
from supplycm.scheduling import fcfs_rule
from supplycm.scheduling import spt_rule
from supplycm.scheduling import wspt_rule
from supplycm.scheduling import edd_rule
from supplycm.scheduling import critical_ratio
from supplycm.scheduling import least_slack
from supplycm.scheduling import moore_hodgson
from supplycm.scheduling import tardiness_calculation
from supplycm.scheduling import total_completion_time
from supplycm.scheduling import total_weighted_tardiness
from supplycm.scheduling import johnsons_rule
from supplycm.scheduling import flow_shop_schedule
from supplycm.scheduling import neh_heuristic
from supplycm.scheduling import cmax_calculation
from supplycm.scheduling import job_shop_schedule
from supplycm.scheduling import open_shop_schedule
from supplycm.scheduling import two_machine_open_shop
from supplycm.scheduling import gantt_chart_data
from supplycm.scheduling import earliest_start_schedule
from supplycm.scheduling import critical_path_method
from supplycm.scheduling import slack_time_calculation
from supplycm.scheduling import pert_expected_duration
from supplycm.scheduling import rpw_priority
from supplycm.scheduling import line_balancing
from supplycm.scheduling import lpt_rule
from supplycm.scheduling import list_scheduling
from supplycm.scheduling import srpt_rule
from supplycm.scheduling import preemptive_spt
from supplycm.scheduling import round_robin_scheduling
from supplycm.scheduling import parallel_machine_cmax
from supplycm.scheduling import parallel_station_scheduling
from supplycm.scheduling import multifit_algorithm
from supplycm.scheduling import batch_scheduling
from supplycm.scheduling import setup_time_aware_scheduling
from supplycm.scheduling import no_wait_scheduling
from supplycm.scheduling import deteriorating_jobs_scheduling
from supplycm.scheduling import learning_curve_scheduling
from supplycm.scheduling import resource_constrained_scheduling
from supplycm.scheduling import lrpt_rule
from supplycm.scheduling import machine_utilization
```

### Networks (29)

```python
from supplycm.network import bfs_shortest_path
from supplycm.network import dfs_traversal
from supplycm.network import bidirectional_search
from supplycm.network import dijkstra_shortest_path
from supplycm.network import a_star_search
from supplycm.network import bellman_ford
from supplycm.network import all_pairs_shortest_path
from supplycm.network import floyd_warshall
from supplycm.network import connected_components
from supplycm.network import strongly_connected_components
from supplycm.network import maximal_clique_bron_kerbosch
from supplycm.network import topological_sort
from supplycm.network import articulation_points
from supplycm.network import bridges_in_graph
from supplycm.network import degree_centrality
from supplycm.network import betweenness_centrality
from supplycm.network import eigenvector_centrality
from supplycm.network import page_rank
from supplycm.network import bipartite_matching
from supplycm.network import max_weight_bipartite_matching
from supplycm.network import min_weight_bipartite_matching
from supplycm.network import kruskal_mst
from supplycm.network import prim_mst
from supplycm.network import ford_fulkerson_max_flow
from supplycm.network import edmonds_karp_max_flow
from supplycm.network import min_cut_max_flow_theorem
from supplycm.network import min_cut_stoer_wagner
from supplycm.network import min_cost_flow_cycle_canceling
from supplycm.network import successive_shortest_path
```

### Network Design (5)

```python
from supplycm.network_design import break_even_analysis
from supplycm.network_design import center_of_gravity
from supplycm.network_design import facility_location_fixed_cost
from supplycm.network_design import network_reliability
from supplycm.network_design import single_source_allocation
```

### Routing & Transportation (30)

```python
from supplycm.routing import tsp_nearest_neighbor
from supplycm.routing import tsp_two_opt
from supplycm.routing import tsp_three_opt
from supplycm.routing import tsp_nearest_insertion
from supplycm.routing import tsp_cheapest_insertion
from supplycm.routing import tsp_farthest_insertion
from supplycm.routing import tsp_held_karp
from supplycm.routing import tsp_christofides
from supplycm.routing import assignment_problem_hungarian
from supplycm.routing import northwest_corner_method
from supplycm.routing import least_cost_method
from supplycm.routing import vogels_approximation
from supplycm.routing import transportation_simplex_modi
from supplycm.routing import transshipment_problem
from supplycm.routing import vehicle_scheduling
from supplycm.routing import vrp_capacitated_greedy
from supplycm.routing import vrp_savings
from supplycm.routing import vrp_sweep
from supplycm.routing import vrp_cluster_first_route_second
from supplycm.routing import split_delivery_vrp
from supplycm.routing import vrp_with_time_windows
from supplycm.routing import multi_depot_vrp
from supplycm.routing import periodic_vrp
from supplycm.routing import pickup_delivery_problem
from supplycm.routing import dial_a_ride
from supplycm.routing import eulerian_tour
from supplycm.routing import chinese_postman
from supplycm.routing import rural_postman
from supplycm.routing import steiner_tree
from supplycm.routing import hamiltonian_path_backtrack
```

### Optimization (30)

```python
from supplycm.optimization import binary_search
from supplycm.optimization import heap_sort
from supplycm.optimization import merge_sort
from supplycm.optimization import quick_sort
from supplycm.optimization import fractional_knapsack
from supplycm.optimization import knapsack_01_dp
from supplycm.optimization import subset_sum
from supplycm.optimization import edit_distance
from supplycm.optimization import longest_increasing_subsequence
from supplycm.optimization import dynamic_programming_lcs
from supplycm.optimization import matrix_chain_multiplication
from supplycm.optimization import convex_hull
from supplycm.optimization import graph_coloring_greedy
from supplycm.optimization import n_queens_backtracking
from supplycm.optimization import ant_colony_optimization
from supplycm.optimization import genetic_algorithm
from supplycm.optimization import particle_swarm_optimization
from supplycm.optimization import simulated_annealing
from supplycm.optimization import tabu_search
from supplycm.optimization import branch_and_bound
from supplycm.optimization import golden_section_search
from supplycm.optimization import gradient_descent
from supplycm.optimization import newton_raphson
from supplycm.optimization import lagrange_multiplier
from supplycm.optimization import simplex_method
from supplycm.optimization import p_median
from supplycm.optimization import bin_packing_first_fit
from supplycm.optimization import bin_packing_best_fit
from supplycm.optimization import bin_packing_first_fit_decreasing
from supplycm.optimization import set_cover_greedy
```

### IoT & Sensors (4)

```python
from supplycm.iot import sensor_data_smoothing
from supplycm.iot import anomaly_detection
from supplycm.iot import realtime_inventory_monitor
from supplycm.iot import iot_data_aggregation
```

### Traceability & Blockchain (4)

```python
from supplycm.blockchain import hash_chain
from supplycm.blockchain import verify_chain
from supplycm.blockchain import provenance_tracking
from supplycm.blockchain import smart_contract_check
```

Each one has a plain-English lesson in the [algorithm library](algorithms/README.md), with a runnable example, self-check questions, and a challenge.
