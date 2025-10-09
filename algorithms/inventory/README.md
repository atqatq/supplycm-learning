---
title: "Inventory Algorithms | supplycm Algorithm Library"
description: "All 60 inventory algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, inventory, inventory, supply chain algorithms"
---

# Inventory (60 algorithms)

How much to buy, when to buy, and how much buffer to keep.

**Levels:** 13 beginner · 27 intermediate · 20 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [Economic Order Quantity (EOQ)](economic_order_quantity.md) | Beginner | EOQ answers the oldest question in purchasing: HOW MUCH should we order? Order often (small batches) and setup costs pile up; order rarely (big batches) and inventory costs pile up |
| 2 | [Inventory Carrying Rate](inventory_carrying_rate.md) | Beginner | Before you can cost inventory, you need the carrying rate: what percentage of an item's value it costs to hold it for a year |
| 3 | [Holding Cost Calculation](holding_cost_calculation.md) | Beginner | Turns the carrying rate into money: unit value x rate x average inventory = annual holding cost |
| 4 | [Economic Production Quantity (EPQ)](economic_production_quantity.md) | Intermediate | EPQ is EOQ's cousin for making items yourself: the machine produces AND demand drains stock at the same time, so peak inventory is lower than the batch size |
| 5 | [EOQ with Backorders](eoq_with_backorders.md) | Advanced | Allowing backorders changes the EOQ math: some demand waits instead of being filled from stock, so peak inventory drops and holding costs fall - at the price of a shortage cost per unit-year of waiting |
| 6 | [EOQ with Quantity Discounts](eoq_quantity_discount.md) | Intermediate | Suppliers offer lower unit prices at bigger quantities |
| 7 | [Reorder Point (ROP)](reorder_point.md) | Beginner | The reorder point is the inventory level that says ORDER NOW |
| 8 | [Safety Stock (Normal Demand)](safety_stock_normal.md) | Intermediate | Safety stock is the cushion against demand surprises during lead time |
| 9 | [Safety Stock with Lead Time Variability](safety_stock_with_lead_time_var.md) | Advanced | Suppliers don't just deliver late sometimes - their DELIVERY TIME wobbles |
| 10 | [Demand During Lead Time](demand_during_lead_time.md) | Beginner | The simplest building block in inventory: how much you expect to sell while waiting for replenishment - demand rate times lead time |
| 11 | [Cycle Service Level from Safety Stock](cycle_service_level.md) | Advanced | This works BACKWARDS from stock to service: given the safety stock you hold, what cycle service level does it actually deliver? It is the honesty check - planners claim 98% service, the math on their buffers sometimes says 87% |
| 12 | [Fill Rate Calculation](fill_rate_calculation.md) | Advanced | Fill rate measures the share of UNITS (not cycles) served from stock |
| 13 | [Expected Backorder Units](expected_backorder.md) | Advanced | Even with safety stock, some cycles end short |
| 14 | [Expected On-Hand Inventory](expected_on_hand.md) | Advanced | Expected on-hand is the average PHYSICAL stock you hold under a given policy - safety stock plus roughly half the order quantity, minus expected shortages |
| 15 | [Stockout Cost](stockout_cost.md) | Beginner | Puts a price on empty shelves: expected shortage units times the penalty per unit - lost margin, expediting, or goodwill |
| 16 | [ABC Analysis](abc_analysis.md) | Beginner | ABC sorts SKUs by the value they move: A items are the vital few (about 20% of items, 80% of value), B the middle, C the trivial many |
| 17 | [XYZ Analysis](xyz_analysis.md) | Intermediate | XYZ measures predictability instead of value: X items sell steadily (low variation), Y items swing with season or trend, Z items are chaotic |
| 18 | [ABC-XYZ Matrix](abc_xyz_matrix.md) | Intermediate | The 3x3 grid where value meets predictability: every item lands in a cell like AX (big and steady - automate and shine) or CZ (small and chaotic - keep it cheap and simple) |
| 19 | [Inventory Position](inventory_position.md) | Beginner | Inventory position = on hand + on order - backorders |
| 20 | [Days of Supply](days_of_supply.md) | Beginner | How many days will current inventory last at the current consumption rate? Stock divided by daily demand |
| 21 | [Inventory Turnover Ratio](inventory_turnover_ratio.md) | Beginner | How many times per year does your inventory sell through completely? Cost of goods sold divided by average inventory |
| 22 | [Inventory-to-Sales Ratio](inventory_to_sales_ratio.md) | Beginner | Inventory value divided by sales value for the same period - a quick 'are we carrying too much relative to business volume?' gauge |
| 23 | [GMROI (Gross Margin Return on Inventory)](gmroi.md) | Intermediate | GMROI asks the retailer's favorite question: for every dollar tied up in inventory, how many dollars of gross margin do we earn back per year? Gross margin divided by average inventory cost |
| 24 | [Inventory Aging Schedule](aging_schedule.md) | Intermediate | Groups inventory by how long it has been sitting: 0-30 days, 31-60, 61-90, 90+ |
| 25 | [Dead Stock Identification](dead_stock_identification.md) | Intermediate | Dead stock is inventory with zero movement over a window - the function flags items whose recent periods show no sales at all |
| 26 | [Slow-Moving Item Detection](slow_moving_detection.md) | Intermediate | One step before dead: slow movers still sell, but too slowly to justify their stock |
| 27 | [Obsolescence Cost](obsolescence_cost.md) | Intermediate | Values the yearly decay of inventory that will never sell at full price: inventory value x obsolescence rate x time held |
| 28 | [FIFO Valuation](fifo_valuation.md) | Intermediate | First-In-First-Out assumes the oldest stock sells first: each sale consumes the oldest cost layers, and what remains on the books is the freshest (usually highest) cost |
| 29 | [LIFO Valuation](lifo_valuation.md) | Advanced | Last-In-First-Out charges sales at the NEWEST costs, leaving old cost layers parked in inventory |
| 30 | [Weighted Average Cost](weighted_average_cost.md) | Intermediate | Blend all cost layers into one average unit cost: total value divided by total units |
| 31 | [Square Root Law of Inventory](square_root_law.md) | Intermediate | Centralize inventory into fewer locations and total safety stock falls with the square ROOT of the location count - halving variability across 4 sites needs only 2x one site's stock, not 4x |
| 32 | [Risk Pooling Effect](risk_pooling.md) | Intermediate | Pooling demand across locations (or products) shrinks relative variability: the pooled standard deviation is smaller than the sum of individual ones, so central stocks cover more with less |
| 33 | [Bullwhip Effect Ratio](bullwhip_effect.md) | Intermediate | Small wiggles in customer demand become giant waves in factory orders as each tier overreacts, batches, and hedges |
| 34 | [Pipeline Inventory](pipeline_inventory.md) | Beginner | Pipeline inventory is stock in transit - ordered, paid for maybe, but sitting on trucks, ships, or trains |
| 35 | [Anticipation Inventory](anticipation_inventory.md) | Intermediate | Anticipation inventory is stock built AHEAD of known demand waves - holiday peaks, promotions, planned shutdowns |
| 36 | [Decoupling Inventory](decoupling_inventory.md) | Intermediate | Decoupling stock sits BETWEEN stages that run at different rhythms, letting each operate independently - fast downstream not starved by slow upstream |
| 37 | [Newsvendor Model](newsvendor_model.md) | Advanced | The newsvendor decides how many newspapers (or croissants, or phones) to stock for ONE selling season with uncertain demand: too many means leftovers, too few means missed sales |
| 38 | [Marginal Analysis Newsvendor](marginal_analysis_newsvendor.md) | Intermediate | A data-driven cousin of the newsvendor: give it discrete demand scenarios with probabilities, and it adds one unit at a time only while the expected gain stays positive |
| 39 | [Optimal Stockout Probability](optimal_stockout_probability.md) | Advanced | Economics in reverse: instead of picking service level then computing stock, this computes the stockout PROBABILITY that maximizes profit, straight from the cost ratios |
| 40 | [Perishable Inventory Order](perishable_inventory.md) | Advanced | The newsvendor, tuned for goods that EXPIRE: bakery items, vaccines, fresh food |
| 41 | [Lot-for-Lot (L4L)](lot_for_lot.md) | Beginner | Order exactly what each period needs - nothing more |
| 42 | [Silver-Meal Heuristic](silver_meal.md) | Advanced | A clever compromise between L4L and big batches: keep EXTENDING one order to cover more future periods while the average cost PER PERIOD keeps falling, and stop the moment it rises |
| 43 | [Least Unit Cost Heuristic](least_unit_cost.md) | Advanced | A sibling heuristic with a different scoreboard: extend the order while the average cost PER UNIT keeps falling, not per period |
| 44 | [Least Period Cost Heuristic](least_period_cost.md) | Advanced | Another member of the family: extend the lot while the TOTAL cost per period covered keeps decreasing - a subtle variant on the same idea with its own stopping point |
| 45 | [Part-Period Balancing (PPB)](part_period_balancing.md) | Advanced | PPB speaks one currency: the part-period (one unit held for one period) |
| 46 | [Periodic Order Quantity (POQ)](periodic_order_quantity.md) | Advanced | POQ asks EOQ to pick a RHYTHM: convert the economic order quantity into an order-every-T-periods cadence, then bundle T periods of demand each time |
| 47 | [Wagner-Whitin (Optimal Lot Sizing)](wagner_whitin.md) | Advanced | The exact solution to dynamic lot sizing: a dynamic program that guarantees the minimum total setup-plus-holding cost over the horizon |
| 48 | [Fixed Order Quantity Lot Sizing](fixed_order_quantity.md) | Intermediate | Order the same fixed quantity whenever stock runs low - the replenishment rhythm of every two-bin system and vending machine |
| 49 | [Periodic Review (R, S) Policy](periodic_review_policy.md) | Intermediate | Check inventory on a SCHEDULE (every Friday, every month) and order up to level S |
| 50 | [(R, Q) Continuous Review Policy](r_q_policy.md) | Intermediate | The classic pair: when inventory position hits reorder point R, order a fixed quantity Q |
| 51 | [(s, S) Min-Max Policy](s_s_policy.md) | Advanced | A twist on (R, Q): when stock hits the minimum s, order enough to reach the MAXIMUM S - so order sizes FLEX with how far you've fallen |
| 52 | [Base-Stock (Order-Up-To) Policy](base_stock_policy.md) | Intermediate | The purest top-up rule: keep inventory POSITION at a base-stock level S - every demand unit triggers an order for one unit |
| 53 | [Joint Replenishment](joint_replenishment.md) | Advanced | Ordering several items from one supplier on one truck shares the major setup cost - but each item still has its own minor costs and holding |
| 54 | [Multi-Echelon Inventory](multi_echelon_inventory.md) | Advanced | A supply chain is a relay: factory -> DC -> stores |
| 55 | [Vendor Managed Inventory (VMI)](vendor_managed_inventory.md) | Intermediate | Under VMI the SUPPLIER watches your stock and decides replenishment - typically holding some inventory on your site (consignment) |
| 56 | [Ordering Cost Allocation](ordering_cost_allocation.md) | Intermediate | One purchase order costs the same whether it carries 3 items or 30 - so who pays the fixed cost? This spreads a total ordering cost across items proportionally to their value or volume, making item-level cost accounting honest instead of arbitrary |
| 57 | [Spare Parts: FSN Classification](spare_parts_fsn.md) | Intermediate | FSN classifies spares by MOVEMENT: Fast movers (issued constantly), Slow movers (occasional), Non-movers (dust) |
| 58 | [Spare Parts: VED Classification](spare_parts_ved.md) | Intermediate | VED ranks spares by CRITICALITY: Vital (the line stops without it), Essential (degradation, big pain), Desirable (nice to have) |
| 59 | [Spare Parts: HML Classification](spare_parts_hml.md) | Intermediate | HML sorts spares by PRICE: High, Medium, Low |
| 60 | [Spare Parts: SDE Classification](spare_parts_sde.md) | Advanced | SDE classifies by ACQUISITION DIFFICULTY: Scarce (imported, sole-source, months of lead time), Difficult (multi-week, few suppliers), Easy (buy anytime) |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_inventory.md](../../flashcards/flashcards_inventory.md)
- Recall drill: [drills/drill_inventory.md](../../drills/drill_inventory.md)
