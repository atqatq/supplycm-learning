---
title: "Flashcards: Inventory | supplycm Learning"
description: "Spaced-repetition flashcards for all 60 supplycm inventory algorithms."
keywords: "flashcards, inventory, supply chain, recall"
---

# Flashcards: Inventory

60 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `economic_order_quantity` do? | Economic Order Quantity (EOQ): EOQ answers the oldest question in purchasing: HOW MUCH should we order? Order often (small batches) and setup costs pile up; order rarely (big batches) and inventory costs pile up. |
| 2 | What does `inventory_carrying_rate` do? | Inventory Carrying Rate: Before you can cost inventory, you need the carrying rate: what percentage of an item's value it costs to hold it for a year. |
| 3 | What does `holding_cost_calculation` do? | Holding Cost Calculation: Turns the carrying rate into money: unit value x rate x average inventory = annual holding cost. |
| 4 | What does `economic_production_quantity` do? | Economic Production Quantity (EPQ): EPQ is EOQ's cousin for making items yourself: the machine produces AND demand drains stock at the same time, so peak inventory is lower than the batch size. |
| 5 | What does `eoq_with_backorders` do? | EOQ with Backorders: Allowing backorders changes the EOQ math: some demand waits instead of being filled from stock, so peak inventory drops and holding costs fall - at the price of a shortage cost per unit-year of waiting. |
| 6 | What does `eoq_quantity_discount` do? | EOQ with Quantity Discounts: Suppliers offer lower unit prices at bigger quantities. |
| 7 | What does `reorder_point` do? | Reorder Point (ROP): The reorder point is the inventory level that says ORDER NOW. |
| 8 | What does `safety_stock_normal` do? | Safety Stock (Normal Demand): Safety stock is the cushion against demand surprises during lead time. |
| 9 | What does `safety_stock_with_lead_time_var` do? | Safety Stock with Lead Time Variability: Suppliers don't just deliver late sometimes - their DELIVERY TIME wobbles. |
| 10 | What does `demand_during_lead_time` do? | Demand During Lead Time: The simplest building block in inventory: how much you expect to sell while waiting for replenishment - demand rate times lead time. |
| 11 | What does `cycle_service_level` do? | Cycle Service Level from Safety Stock: This works BACKWARDS from stock to service: given the safety stock you hold, what cycle service level does it actually deliver? It is the honesty check - planners claim 98% service, the math on their buffers sometimes says 87%. |
| 12 | What does `fill_rate_calculation` do? | Fill Rate Calculation: Fill rate measures the share of UNITS (not cycles) served from stock. |
| 13 | What does `expected_backorder` do? | Expected Backorder Units: Even with safety stock, some cycles end short. |
| 14 | What does `expected_on_hand` do? | Expected On-Hand Inventory: Expected on-hand is the average PHYSICAL stock you hold under a given policy - safety stock plus roughly half the order quantity, minus expected shortages. |
| 15 | What does `stockout_cost` do? | Stockout Cost: Puts a price on empty shelves: expected shortage units times the penalty per unit - lost margin, expediting, or goodwill. |
| 16 | What does `abc_analysis` do? | ABC Analysis: ABC sorts SKUs by the value they move: A items are the vital few (about 20% of items, 80% of value), B the middle, C the trivial many. |
| 17 | What does `xyz_analysis` do? | XYZ Analysis: XYZ measures predictability instead of value: X items sell steadily (low variation), Y items swing with season or trend, Z items are chaotic. |
| 18 | What does `abc_xyz_matrix` do? | ABC-XYZ Matrix: The 3x3 grid where value meets predictability: every item lands in a cell like AX (big and steady - automate and shine) or CZ (small and chaotic - keep it cheap and simple). |
| 19 | What does `inventory_position` do? | Inventory Position: Inventory position = on hand + on order - backorders. |
| 20 | What does `days_of_supply` do? | Days of Supply: How many days will current inventory last at the current consumption rate? Stock divided by daily demand. |
| 21 | What does `inventory_turnover_ratio` do? | Inventory Turnover Ratio: How many times per year does your inventory sell through completely? Cost of goods sold divided by average inventory. |
| 22 | What does `inventory_to_sales_ratio` do? | Inventory-to-Sales Ratio: Inventory value divided by sales value for the same period - a quick 'are we carrying too much relative to business volume?' gauge. |
| 23 | What does `gmroi` do? | GMROI (Gross Margin Return on Inventory): GMROI asks the retailer's favorite question: for every dollar tied up in inventory, how many dollars of gross margin do we earn back per year? Gross margin divided by average inventory cost. |
| 24 | What does `aging_schedule` do? | Inventory Aging Schedule: Groups inventory by how long it has been sitting: 0-30 days, 31-60, 61-90, 90+. |
| 25 | What does `dead_stock_identification` do? | Dead Stock Identification: Dead stock is inventory with zero movement over a window - the function flags items whose recent periods show no sales at all. |
| 26 | What does `slow_moving_detection` do? | Slow-Moving Item Detection: One step before dead: slow movers still sell, but too slowly to justify their stock. |
| 27 | What does `obsolescence_cost` do? | Obsolescence Cost: Values the yearly decay of inventory that will never sell at full price: inventory value x obsolescence rate x time held. |
| 28 | What does `fifo_valuation` do? | FIFO Valuation: First-In-First-Out assumes the oldest stock sells first: each sale consumes the oldest cost layers, and what remains on the books is the freshest (usually highest) cost. |
| 29 | What does `lifo_valuation` do? | LIFO Valuation: Last-In-First-Out charges sales at the NEWEST costs, leaving old cost layers parked in inventory. |
| 30 | What does `weighted_average_cost` do? | Weighted Average Cost: Blend all cost layers into one average unit cost: total value divided by total units. |
| 31 | What does `square_root_law` do? | Square Root Law of Inventory: Centralize inventory into fewer locations and total safety stock falls with the square ROOT of the location count - halving variability across 4 sites needs only 2x one site's stock, not 4x. |
| 32 | What does `risk_pooling` do? | Risk Pooling Effect: Pooling demand across locations (or products) shrinks relative variability: the pooled standard deviation is smaller than the sum of individual ones, so central stocks cover more with less. |
| 33 | What does `bullwhip_effect` do? | Bullwhip Effect Ratio: Small wiggles in customer demand become giant waves in factory orders as each tier overreacts, batches, and hedges. |
| 34 | What does `pipeline_inventory` do? | Pipeline Inventory: Pipeline inventory is stock in transit - ordered, paid for maybe, but sitting on trucks, ships, or trains. |
| 35 | What does `anticipation_inventory` do? | Anticipation Inventory: Anticipation inventory is stock built AHEAD of known demand waves - holiday peaks, promotions, planned shutdowns. |
| 36 | What does `decoupling_inventory` do? | Decoupling Inventory: Decoupling stock sits BETWEEN stages that run at different rhythms, letting each operate independently - fast downstream not starved by slow upstream. |
| 37 | What does `newsvendor_model` do? | Newsvendor Model: The newsvendor decides how many newspapers (or croissants, or phones) to stock for ONE selling season with uncertain demand: too many means leftovers, too few means missed sales. |
| 38 | What does `marginal_analysis_newsvendor` do? | Marginal Analysis Newsvendor: A data-driven cousin of the newsvendor: give it discrete demand scenarios with probabilities, and it adds one unit at a time only while the expected gain stays positive. |
| 39 | What does `optimal_stockout_probability` do? | Optimal Stockout Probability: Economics in reverse: instead of picking service level then computing stock, this computes the stockout PROBABILITY that maximizes profit, straight from the cost ratios. |
| 40 | What does `perishable_inventory` do? | Perishable Inventory Order: The newsvendor, tuned for goods that EXPIRE: bakery items, vaccines, fresh food. |
| 41 | What does `lot_for_lot` do? | Lot-for-Lot (L4L): Order exactly what each period needs - nothing more. |
| 42 | What does `silver_meal` do? | Silver-Meal Heuristic: A clever compromise between L4L and big batches: keep EXTENDING one order to cover more future periods while the average cost PER PERIOD keeps falling, and stop the moment it rises. |
| 43 | What does `least_unit_cost` do? | Least Unit Cost Heuristic: A sibling heuristic with a different scoreboard: extend the order while the average cost PER UNIT keeps falling, not per period. |
| 44 | What does `least_period_cost` do? | Least Period Cost Heuristic: Another member of the family: extend the lot while the TOTAL cost per period covered keeps decreasing - a subtle variant on the same idea with its own stopping point. |
| 45 | What does `part_period_balancing` do? | Part-Period Balancing (PPB): PPB speaks one currency: the part-period (one unit held for one period). |
| 46 | What does `periodic_order_quantity` do? | Periodic Order Quantity (POQ): POQ asks EOQ to pick a RHYTHM: convert the economic order quantity into an order-every-T-periods cadence, then bundle T periods of demand each time. |
| 47 | What does `wagner_whitin` do? | Wagner-Whitin (Optimal Lot Sizing): The exact solution to dynamic lot sizing: a dynamic program that guarantees the minimum total setup-plus-holding cost over the horizon. |
| 48 | What does `fixed_order_quantity` do? | Fixed Order Quantity Lot Sizing: Order the same fixed quantity whenever stock runs low - the replenishment rhythm of every two-bin system and vending machine. |
| 49 | What does `periodic_review_policy` do? | Periodic Review (R, S) Policy: Check inventory on a SCHEDULE (every Friday, every month) and order up to level S. |
| 50 | What does `r_q_policy` do? | (R, Q) Continuous Review Policy: The classic pair: when inventory position hits reorder point R, order a fixed quantity Q. |
| 51 | What does `s_s_policy` do? | (s, S) Min-Max Policy: A twist on (R, Q): when stock hits the minimum s, order enough to reach the MAXIMUM S - so order sizes FLEX with how far you've fallen. |
| 52 | What does `base_stock_policy` do? | Base-Stock (Order-Up-To) Policy: The purest top-up rule: keep inventory POSITION at a base-stock level S - every demand unit triggers an order for one unit. |
| 53 | What does `joint_replenishment` do? | Joint Replenishment: Ordering several items from one supplier on one truck shares the major setup cost - but each item still has its own minor costs and holding. |
| 54 | What does `multi_echelon_inventory` do? | Multi-Echelon Inventory: A supply chain is a relay: factory -> DC -> stores. |
| 55 | What does `vendor_managed_inventory` do? | Vendor Managed Inventory (VMI): Under VMI the SUPPLIER watches your stock and decides replenishment - typically holding some inventory on your site (consignment). |
| 56 | What does `ordering_cost_allocation` do? | Ordering Cost Allocation: One purchase order costs the same whether it carries 3 items or 30 - so who pays the fixed cost? This spreads a total ordering cost across items proportionally to their value or volume, making item-level cost accounting honest instead of arbitrary. |
| 57 | What does `spare_parts_fsn` do? | Spare Parts: FSN Classification: FSN classifies spares by MOVEMENT: Fast movers (issued constantly), Slow movers (occasional), Non-movers (dust). |
| 58 | What does `spare_parts_ved` do? | Spare Parts: VED Classification: VED ranks spares by CRITICALITY: Vital (the line stops without it), Essential (degradation, big pain), Desirable (nice to have). |
| 59 | What does `spare_parts_hml` do? | Spare Parts: HML Classification: HML sorts spares by PRICE: High, Medium, Low. |
| 60 | What does `spare_parts_sde` do? | Spare Parts: SDE Classification: SDE classifies by ACQUISITION DIFFICULTY: Scarce (imported, sole-source, months of lead time), Difficult (multi-week, few suppliers), Easy (buy anytime). |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
