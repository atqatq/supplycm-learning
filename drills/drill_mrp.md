---
title: "Recall Drill: MRP & Production Planning | supplycm Learning"
description: "Active-recall drill with answer key covering all 30 supplycm mrp & production planning algorithms."
keywords: "drill, recall, mrp, supply chain practice"
---

# Recall Drill: MRP & Production Planning

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**BOM Explosion** (`bom_explosion`)

1. Why does item 3 need 400 units, not 100?
2. What happens with scrap in real factories?
3. Demand for 50 bikes, wheels also sold as spares. How to handle?

**Low-Level Coding** (`low_level_coding`)

4. What breaks if you skip low-level coding?
5. Item X appears at level 1 in one product and level 3 in another. Its code?
6. Who computes level codes in real systems?

**Where-Used Query** (`where_used_query`)

7. Component used by 5 parents, one is being discontinued. What now?
8. Where-used vs pegging - difference?
9. Why is this query critical for substitutions?

**Modular BOM** (`modular_bom`)

10. Why is module forecasting more accurate than variant forecasting?
11. A new variant mixes modules in new ratios. What changes?
12. Where do module ratios come from?

**Planning BOM (Option Percentages)** (`planning_bom`)

13. Where do the percentages come from?
14. Percentages sum to 0.95. Problem?
15. One color trends from 20% to 35% over months. Action?

**Shrinkage Factor** (`shrinkage_factor`)

16. Why divide by (1 - rate) instead of just adding 5%?
17. Shrinkage 40% - alarm bells?
18. Different shrinkage per step in a 3-step process. Now what?

**Safety Lead Time** (`safety_lead_time`)

19. Safety lead time vs safety stock - what's the difference?
20. When is safety lead time the cheaper protection?
21. Supplier improves to near-perfect timing. Action?

**Lead Time Offsetting** (`lead_time_offsetting`)

22. Lead time 2 means the release lands where?
23. Release date falls in the past. What does that mean?
24. Two components, lead times 1 and 4, same due date. Which nags first?

**Backflush** (`backflush`)

25. What is backflush's big risk?
26. When should you NOT backflush?
27. How do healthy backflush users keep stock honest?

**MRP Calculation** (`mrp_calculation`)

28. What are the four rows of an MRP record?
29. On hand 5, gross 10 - net requirement?
30. Why do planned orders release EARLIER than receipts?

**Master Production Schedule (MPS)** (`master_production_schedule`)

31. What does 'consuming the forecast' mean?
32. Orders exceed forecast in a period - what does MPS do?
33. Why produce in lot sizes inside MPS?

**Available-to-Promise (ATP)** (`available_to_promise`)

34. Why isn't ATP just 'on hand'?
35. ATP goes negative in week 3. Meaning?
36. Who should 'own' ATP numbers?

**Capable-to-Promise (CTP)** (`capable_to_promise`)

37. ATP vs CTP in one line?
38. What makes an order infeasible (-1)?
39. Why is CTP harder to keep accurate than ATP?

**Lot-for-Lot (L4L)** (`lot_size_rule_l4l`)

40. What does L4L minimize, and what does it ignore?
41. When is L4L clearly the right rule?
42. How does L4L differ from EOQ?

**Fixed Order Quantity (FOQ)** (`lot_size_rule_foq`)

43. What happens when the requirement is 10 and FOQ is 50?
44. Why do suppliers love FOQ?
45. When does FOQ become expensive?

**Period Order Quantity (POQ)** (`lot_size_rule_poq`)

46. How does POQ choose quantities?
47. POQ period 1 equals which rule?
48. Longer POQ period: what rises and what falls?

**Economic Part Period (EPP) Lot Sizing** (`lot_size_rule_epr`)

49. What is a 'part-period'?
50. How is the EPP threshold computed?
51. Demand spikes once then vanishes. What does EPP do?

**Minimum Order Quantity (MOQ)** (`minimum_order_quantity`)

52. What does MOQ do to inventory when demand is small?
53. Requirement is 49, MOQ is 50. Order how much?
54. How can buyers fight bad MOQ effects?

**Maximum Order Quantity (MaxOQ)** (`maximum_order_quantity`)

55. What happens to demand the cap cannot cover this period?
56. Why set caps at all if MRP says order 150?
57. Cap forces a split - what should you check next?

**Order Multiples** (`order_multiples`)

58. Round up or down to the multiple?
59. Order 24 with multiple 24 - any change?
60. Multiple 100 on an item needing 5/year. Problem?

**Quantity Discount Lot Sizing** (`quantity_discount_mrp`)

61. What two costs fight when you take a discount?
62. Discount saves 2/unit on 120 extra units held one period, holding 1/unit/period. Take it?
63. When is chasing discounts a trap?

**Capacity Requirements Planning (CRP)** (`capacity_requirements_planning`)

64. What inputs does CRP need beyond MRP?
65. CRP shows an overload 4 weeks out. Best responses?
66. Why does CRP sometimes load 'past' work centers unnecessarily?

**Demand Time Fence** (`demand_time_fence`)

67. What counts as demand INSIDE the fence?
68. Sales insists on adding 20 units inside the fence. Who approves?
69. Where should the fence sit?

**Planning Time Fence** (`planning_time_fence`)

70. Planning fence vs demand fence - what does each control?
71. Why plan lot-for-lot inside the fence?
72. Fence too far out - symptom?

**Pegging** (`pegging`)

73. Pegging vs where-used - what's the difference?
74. A shortage hits component 3. What does pegging let you do?
75. Why do ratios (qty per) matter in pegging?

**Phantom BOM Handling** (`phantom_bom_handling`)

76. Why do phantoms exist at all?
77. What would happen if a phantom were treated as real?
78. When is an assembly NOT a phantom?

**Cycle Counting Plan** (`cycle_counting`)

79. Why count A items 12 times a year and C items once?
80. What accuracy level should cycle counting target?
81. A count is off by 3%. Fix the number and move on?

**Rough-Cut Capacity Planning (RCCP)** (`rough_cut_capacity_planning`)

82. RCCP vs detailed CRP - difference?
83. Resource load is 120% for two periods. Options?
84. Which resources belong in an RCCP check?

**Drum-Buffer-Rope (DBR)** (`drum_buffer_rope`)

85. What do the drum, buffer, and rope each represent?
86. Non-bottleneck machines idle sometimes. Waste?
87. The bottleneck gets faster. What must change?

**Kanban Card Sizing** (`kaban_sizing`)

88. What does each kanban card authorize?
89. Demand doubles. What happens to card count?
90. Why multiply by a safety factor?

Total: 90 questions.

## Part 2 - Answer key

1. Because 100 parents need 100 of item 2, and each item 2 needs 4 of item 3 - explosion multiplies down the tree.
2. You inflate quantities by a scrap factor first - the plain explosion assumes perfect yields.
3. Add spare demand as independent demand on the wheel - explosion covers only the dependent part.
4. MRP might plan the shared part too early, from one parent only, and miss the other parent's requirement.
5. 3 - the LOWEST (deepest) level anywhere in any bill.
6. The MRP system itself, after every BOM change - but you should understand what it is doing.
7. 4 parents still depend on it - demand drops but does not vanish; update forecasts accordingly.
8. Where-used lists ALL possible parents statically; pegging traces a specific requirement to ITS source order.
9. You must know every affected product BEFORE switching a part - surprises here are recalls.
10. Variants split demand into noisy streams; modules aggregate it - noise cancels and percentages are stabler.
11. Only the ratio table - the module plan adapts without new forecasting models.
12. Recent actual sales mix, updated regularly - stale ratios quietly mis-plan.
13. Historical sales mix - adjusted for known shifts like a new color launch.
14. Yes - 5% of demand is unplanned; percentages should cover 100% or you knowingly hold a buffer.
15. Update the planning percentages gradually - chasing one month's mix overcorrects.
16. Because the loss applies to the STARTING quantity - dividing compounds correctly; adding under-covers.
17. Yes - that is a process problem, not a planning parameter; investigate before planning around it.
18. Apply each step's factor in sequence - the compound loss is bigger than any single step suggests.
19. Time buffer vs quantity buffer: release earlier vs hold more. Pick based on whether lateness or variability dominates.
20. Steady demand with unreliable timing - extra stock would just sit, while early release costs almost nothing.
21. Remove the buffer gradually - permanent cushions hide real performance forever.
22. Two periods before the need date - receipt week minus 2.
23. You are already late - expedite, reduce the requirement, or accept a miss; the system is telling the truth.
24. The 4-week one - offsetting is per component, so plans release at different times.
25. Silent drift: scrap, substitutions, and BOM errors accumulate as phantom inventory discrepancies.
26. High-scrap processes, expensive tracked components, or where batch records are legally required.
27. Cycle counting plus exception alerts for unusually large deductions.
28. Gross requirements, scheduled receipts, projected on hand, and planned orders (with their releases).
29. 5 - MRP plans only the gap, never the gross.
30. Lead time offsetting - a receipt in week 4 with 1-week lead time must release in week 3.
31. Real orders replace forecasted demand line by line, so production plans real remaining need, not forecast plus orders double-counted.
32. The forecast is fully consumed and the excess pulls production or inventory forward - watch the on-hand row.
33. Real ovens, machines, and setups come in economical chunks - lot sizing turns continuous need into buildable batches.
34. Because receipts arrive (good) and orders already promised (bad) both change the real promise-able pool.
35. Over-promised - new orders there need expediting, delay, or a polite no; the number forces the conversation.
36. Operations owns the calculation; sales consumes it - shared visibility beats both sides keeping private math.
37. ATP checks stock; CTP checks stock AND the ability to make more in time.
38. Capacity and lead time math cannot land it anywhere within the horizon - quote a later date or add capacity.
39. It needs live capacity data from the shop floor - stale routings or calendars quietly poison every promise.
40. It minimizes inventory but ignores setup cost - order every period with demand, however small.
41. When holding costs dwarf setup costs - perishables, custom items, cheap changeovers.
42. EOQ fixes one quantity for efficiency; L4L flexes with demand to eliminate holding.
43. You order 50 - the extra 40 waits as inventory for future periods.
44. Predictable volumes mean stable production runs and easier logistics on their side.
45. Erratic small demands - rounding waste piles up; consider L4L or period quantities instead.
46. It sums the net requirements across the chosen number of periods whenever an order is placed.
47. Lot-for-lot - one period per order.
48. Holding cost rises; setup count (and cost) falls - the balance is the whole game.
49. One unit held for one period - the common currency that lets setup cost and holding cost be compared.
50. Roughly setup_cost / holding_cost - the number of part-periods a setup can 'afford'.
51. It covers the spike in one lot and stops extending - the holding budget naturally refuses to carry dead demand.
52. Inflates it - you hold the difference between floor and need until it is consumed.
53. 50 - just under the floor still triggers the floor.
54. Negotiate lower minimums, mix SKUs on one PO, or hold supplier-managed stock nearby.
55. It moves to a later order - which may violate a due date unless you pre-build or expedite.
56. Because the machine makes 100 max per run - MRP plans need, caps keep plans physically possible.
57. Capacity in the following period for the leftover, and holding cost of any earlier pre-build.
58. Up - rounding down would violate the requirement; the small excess becomes inventory.
59. None - it is already a whole multiple.
60. Huge - the multiple forces 20x the annual need; renegotiate pack size or find another supplier.
61. Unit price saving vs extra holding cost of the bigger lot.
62. 2 x 120 = 240 saved vs 120 holding - yes, if the leftover truly sells next period.
63. When it distorts the whole plan - cash tied up, obsolescence risk, or the 'discount' applies to stuff you barely need.
64. Routings (which work centers, how long per unit) and each center's capacity.
65. Shift planned orders earlier (pre-build), add capacity (shifts/overtime), or re-plan the orders - all cheap NOW, costly later.
66. Planned orders include queued work - mature setups subtract past-due portions or they double count.
67. Actual customer orders only - forecasts are ignored because production is already committed.
68. An escalation - it disrupts committed supply; someone senior trades off cost and customer impact.
69. Roughly at the cumulative lead time - changes before that point are physically hard to honor.
70. Demand fence controls WHAT demand counts; planning fence controls HOW lot sizes are chosen.
71. To avoid big rigid lots churning near-term capacity - flexibility first when the time is short.
72. The plan gets rigid and unresponsive; too near - MRP stays nervous. Tune by watching message churn.
73. Where-used lists possible parents; pegging ties a SPECIFIC requirement to its actual source orders.
74. Tell each affected customer order what happens to it - and choose which to save.
75. They convert parent quantities into child needs - the arithmetic behind every trace.
76. To organize drawings and engineering structure without forcing planning of items nobody stocks.
77. MRP would demand you build and stock an assembly that is consumed instantly - pure noise.
78. When it is actually built, tested, and stored as a sellable or service part.
79. A errors cost the most and move fastest - accuracy effort should follow value at risk.
80. Commonly 95-99% by class (A highest) - below that, MRP orders start protecting against your own data.
81. No - investigate the root cause (process, location, transaction) or the error returns next count.
82. RCCP checks a FEW critical resources roughly; CRP schedules every work center precisely.
83. Pre-build earlier, add shifts, outsource, or level the plan - RCCP exists to force that choice early.
84. The chronic bottlenecks - constraint machines, key skills, critical tooling - not every station.
85. Drum: the constraint's pace; buffer: protection time/stock before it; rope: release tied to that pace.
86. Not really - their idle time is the price of keeping the constraint fed and on schedule.
87. The whole system's pace - the drum beats differently, so buffers and release rates are re-tuned.
88. One container of parts - total cards x container size is your WIP ceiling.
89. It roughly doubles - recompute, or the line starves between replenishments.
90. Real lead times wobble - the factor absorbs ordinary variability without a stockout every week.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
