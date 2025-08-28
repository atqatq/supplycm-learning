---
title: "Flashcards: MRP & Production Planning | supplycm Learning"
description: "Spaced-repetition flashcards for all 30 supplycm mrp & production planning algorithms."
keywords: "flashcards, mrp, supply chain, recall"
---

# Flashcards: MRP & Production Planning

30 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `bom_explosion` do? | BOM Explosion: A bill of materials says what a product is made of. |
| 2 | What does `low_level_coding` do? | Low-Level Coding: Low-level coding stamps every part with the LOWEST level where it appears anywhere in the BOM tree. |
| 3 | What does `where_used_query` do? | Where-Used Query: The reverse of explosion: given a component, find every parent that uses it. |
| 4 | What does `modular_bom` do? | Modular BOM: For product families built from modules (laptops: screen + CPU + case), a modular BOM plans MODULES instead of every finished-goods variant. |
| 5 | What does `planning_bom` do? | Planning BOM (Option Percentages): A planning BOM replaces exact variant counts with percentages: 'of 1,000 units, 30% will be red, 50% blue, 20% green'. |
| 6 | What does `shrinkage_factor` do? | Shrinkage Factor: Shrinkage is the share that disappears: scrap on the line, damage, theft, yield loss. |
| 7 | What does `safety_lead_time` do? | Safety Lead Time: Safety lead time is a buffer in TIME, not units: order earlier than the standard lead time says. |
| 8 | What does `lead_time_offsetting` do? | Lead Time Offsetting: If a part needs 3 weeks and you must HAVE it in week 8, the ORDER must release in week 5. |
| 9 | What does `backflush` do? | Backflush: Instead of recording every part issued to the floor, backflush DEDUCTS the whole recipe when the finished unit is reported done: 100 bikes done means 200 wheels and 100 frames leave inventory automatically. |
| 10 | What does `mrp_calculation` do? | MRP Calculation: The full MRP record for one item, period by period: gross requirements minus on hand and scheduled receipts leaves net requirements, which become planned receipts - shifted earlier by lead time into planned orders. |
| 11 | What does `master_production_schedule` do? | Master Production Schedule (MPS): The MPS is the promise the factory makes: how many to build each period after real orders consume the forecast. |
| 12 | What does `available_to_promise` do? | Available-to-Promise (ATP): ATP answers the sales question 'if a customer orders TODAY, can I promise it?' - inventory plus arriving receipts minus orders already promised. |
| 13 | What does `capable_to_promise` do? | Capable-to-Promise (CTP): CTP goes one step past ATP: not 'what do we have' but 'what could we BUILD' given capacity and lead times. |
| 14 | What does `lot_size_rule_l4l` do? | Lot-for-Lot (L4L): Lot-for-lot orders exactly the net requirement, period by period - no more, no less. |
| 15 | What does `lot_size_rule_foq` do? | Fixed Order Quantity (FOQ): FOQ always orders the same amount - 100 is 100, every time, possibly rounding up past the need. |
| 16 | What does `lot_size_rule_poq` do? | Period Order Quantity (POQ): POQ orders several periods of demand at once - 'order every 3 weeks' instead of every week. |
| 17 | What does `lot_size_rule_epr` do? | Economic Part Period (EPP) Lot Sizing: EPP balances setup and holding automatically: compute how many 'part-periods' (units x periods held) of holding one setup can justify, then extend an order only while the accumulated holding stays under that budget. |
| 18 | What does `minimum_order_quantity` do? | Minimum Order Quantity (MOQ): Suppliers set minimums: 'at least 100 units or we cannot ship'. |
| 19 | What does `maximum_order_quantity` do? | Maximum Order Quantity (MaxOQ): The opposite guardrail: caps how big a single order may be - capacity limits, truck sizes, budget rules, or cash constraints. |
| 20 | What does `order_multiples` do? | Order Multiples: Many items ship in packs: 12 per box, 50 per pallet. |
| 21 | What does `quantity_discount_mrp` do? | Quantity Discount Lot Sizing: Suppliers drop the unit price at quantity breaks: 100+ units cost less each. |
| 22 | What does `capacity_requirements_planning` do? | Capacity Requirements Planning (CRP): CRP takes MRP's planned orders and pushes them through routings - each item's work centers and times - to compute the load on EVERY work center, period by period. |
| 23 | What does `demand_time_fence` do? | Demand Time Fence: Inside the demand time fence, planning freezes: only real customer orders count, not forecast changes - the factory is already committed. |
| 24 | What does `planning_time_fence` do? | Planning Time Fence: Inside the planning time fence, the system stops changing lot sizes automatically: it plans lot-for-lot inside, fixed-lot outside. |
| 25 | What does `pegging` do? | Pegging: Pegging answers 'WHERE did this component requirement come from?'. |
| 26 | What does `phantom_bom_handling` do? | Phantom BOM Handling: A phantom is a logical grouping in the BOM that is never built or stocked as a real item - an assembly that exists on paper only. |
| 27 | What does `cycle_counting` do? | Cycle Counting Plan: Instead of one dreaded annual wall-to-wall count, cycle counting counts a few items every day all year - A items often, C items rarely. |
| 28 | What does `rough_cut_capacity_planning` do? | Rough-Cut Capacity Planning (RCCP): Before trusting a production plan, RCCP asks: can our key resources actually DO this? Multiply planned quantities by per-unit resource needs, compare with capacities, and get the load per resource. |
| 29 | What does `drum_buffer_rope` do? | Drum-Buffer-Rope (DBR): Theory of Constraints in one schedule: the bottleneck (drum) sets the pace for everything; a time buffer protects it from starvation; the rope links release of new work to the drum's actual capacity. |
| 30 | What does `kaban_sizing` do? | Kanban Card Sizing: Kanban controls work-in-progress with cards: each card authorizes one container. |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
