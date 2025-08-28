---
title: "MRP & Production Planning Algorithms | supplycm Algorithm Library"
description: "All 30 mrp & production planning algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, mrp, mrp & production planning, supply chain algorithms"
---

# MRP & Production Planning (30 algorithms)

Turn a production plan into purchase orders and work orders.

**Levels:** 9 beginner · 16 intermediate · 5 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [BOM Explosion](bom_explosion.md) | Beginner | A bill of materials says what a product is made of |
| 2 | [Low-Level Coding](low_level_coding.md) | Intermediate | Low-level coding stamps every part with the LOWEST level where it appears anywhere in the BOM tree |
| 3 | [Where-Used Query](where_used_query.md) | Beginner | The reverse of explosion: given a component, find every parent that uses it |
| 4 | [Modular BOM](modular_bom.md) | Intermediate | For product families built from modules (laptops: screen + CPU + case), a modular BOM plans MODULES instead of every finished-goods variant |
| 5 | [Planning BOM (Option Percentages)](planning_bom.md) | Intermediate | A planning BOM replaces exact variant counts with percentages: 'of 1,000 units, 30% will be red, 50% blue, 20% green' |
| 6 | [Shrinkage Factor](shrinkage_factor.md) | Beginner | Shrinkage is the share that disappears: scrap on the line, damage, theft, yield loss |
| 7 | [Safety Lead Time](safety_lead_time.md) | Beginner | Safety lead time is a buffer in TIME, not units: order earlier than the standard lead time says |
| 8 | [Lead Time Offsetting](lead_time_offsetting.md) | Beginner | If a part needs 3 weeks and you must HAVE it in week 8, the ORDER must release in week 5 |
| 9 | [Backflush](backflush.md) | Intermediate | Instead of recording every part issued to the floor, backflush DEDUCTS the whole recipe when the finished unit is reported done: 100 bikes done means 200 wheels and 100 frames leave inventory automatically |
| 10 | [MRP Calculation](mrp_calculation.md) | Intermediate | The full MRP record for one item, period by period: gross requirements minus on hand and scheduled receipts leaves net requirements, which become planned receipts - shifted earlier by lead time into planned orders |
| 11 | [Master Production Schedule (MPS)](master_production_schedule.md) | Intermediate | The MPS is the promise the factory makes: how many to build each period after real orders consume the forecast |
| 12 | [Available-to-Promise (ATP)](available_to_promise.md) | Intermediate | ATP answers the sales question 'if a customer orders TODAY, can I promise it?' - inventory plus arriving receipts minus orders already promised |
| 13 | [Capable-to-Promise (CTP)](capable_to_promise.md) | Intermediate | CTP goes one step past ATP: not 'what do we have' but 'what could we BUILD' given capacity and lead times |
| 14 | [Lot-for-Lot (L4L)](lot_size_rule_l4l.md) | Beginner | Lot-for-lot orders exactly the net requirement, period by period - no more, no less |
| 15 | [Fixed Order Quantity (FOQ)](lot_size_rule_foq.md) | Beginner | FOQ always orders the same amount - 100 is 100, every time, possibly rounding up past the need |
| 16 | [Period Order Quantity (POQ)](lot_size_rule_poq.md) | Intermediate | POQ orders several periods of demand at once - 'order every 3 weeks' instead of every week |
| 17 | [Economic Part Period (EPP) Lot Sizing](lot_size_rule_epr.md) | Advanced | EPP balances setup and holding automatically: compute how many 'part-periods' (units x periods held) of holding one setup can justify, then extend an order only while the accumulated holding stays under that budget |
| 18 | [Minimum Order Quantity (MOQ)](minimum_order_quantity.md) | Beginner | Suppliers set minimums: 'at least 100 units or we cannot ship' |
| 19 | [Maximum Order Quantity (MaxOQ)](maximum_order_quantity.md) | Intermediate | The opposite guardrail: caps how big a single order may be - capacity limits, truck sizes, budget rules, or cash constraints |
| 20 | [Order Multiples](order_multiples.md) | Beginner | Many items ship in packs: 12 per box, 50 per pallet |
| 21 | [Quantity Discount Lot Sizing](quantity_discount_mrp.md) | Advanced | Suppliers drop the unit price at quantity breaks: 100+ units cost less each |
| 22 | [Capacity Requirements Planning (CRP)](capacity_requirements_planning.md) | Advanced | CRP takes MRP's planned orders and pushes them through routings - each item's work centers and times - to compute the load on EVERY work center, period by period |
| 23 | [Demand Time Fence](demand_time_fence.md) | Intermediate | Inside the demand time fence, planning freezes: only real customer orders count, not forecast changes - the factory is already committed |
| 24 | [Planning Time Fence](planning_time_fence.md) | Intermediate | Inside the planning time fence, the system stops changing lot sizes automatically: it plans lot-for-lot inside, fixed-lot outside |
| 25 | [Pegging](pegging.md) | Intermediate | Pegging answers 'WHERE did this component requirement come from?' |
| 26 | [Phantom BOM Handling](phantom_bom_handling.md) | Advanced | A phantom is a logical grouping in the BOM that is never built or stocked as a real item - an assembly that exists on paper only |
| 27 | [Cycle Counting Plan](cycle_counting.md) | Intermediate | Instead of one dreaded annual wall-to-wall count, cycle counting counts a few items every day all year - A items often, C items rarely |
| 28 | [Rough-Cut Capacity Planning (RCCP)](rough_cut_capacity_planning.md) | Intermediate | Before trusting a production plan, RCCP asks: can our key resources actually DO this? Multiply planned quantities by per-unit resource needs, compare with capacities, and get the load per resource |
| 29 | [Drum-Buffer-Rope (DBR)](drum_buffer_rope.md) | Advanced | Theory of Constraints in one schedule: the bottleneck (drum) sets the pace for everything; a time buffer protects it from starvation; the rope links release of new work to the drum's actual capacity |
| 30 | [Kanban Card Sizing](kaban_sizing.md) | Intermediate | Kanban controls work-in-progress with cards: each card authorizes one container |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_mrp.md](../../flashcards/flashcards_mrp.md)
- Recall drill: [drills/drill_mrp.md](../../drills/drill_mrp.md)
