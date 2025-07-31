---
title: "Recall Drill: Warehouse | supplycm Learning"
description: "Active-recall drill with answer key covering all 10 supplycm warehouse algorithms."
keywords: "drill, recall, warehouse, supply chain practice"
---

# Recall Drill: Warehouse

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Warehouse Slotting (ABC)** (`warehouse_slotting_abc`)

1. What data decides an item's zone?
2. How often should you re-slot?
3. Why does slotting beat 'work faster' as a lever?

**Warehouse Layout Optimization** (`warehouse_layout_optimization`)

4. What makes a slot 'good'?
5. One SKU explodes in demand after a viral moment. Layout action?
6. What competes with putting everything in the golden zone?

**Putaway Strategy** (`putaway_strategy`)

7. Why does bad putaway slow down PICKING later?
8. What does 'directed putaway' add over free putaway?
9. When would you knowingly put a fast item in a bad slot?

**Order Picking Wave Planning** (`order_picking_wave`)

10. What trades off when you choose fewer waves?
11. How do carrier cutoff times shape wave planning?
12. When does wave picking lose to zone or batch picking?

**S-Shape (Serpentine) Picking Route** (`s_shape_routing`)

13. When does S-shape waste distance?
14. Name two alternatives to S-shape.
15. Why is simple routing often best in practice?

**Return (Back-and-Forth) Routing** (`return_routing`)

16. When does return routing beat S-shape?
17. What does the position data in the example represent?
18. Can you mix return and S-shape on one route?

**TSP-Based Picking** (`traveling_salesman_picking`)

19. Why not always use TSP routing in warehouses?
20. S-shape vs TSP on a 30-line order - practical winner?
21. What data makes TSP picking accurate?

**Pallet Building** (`pallet_building`)

22. Why place the biggest items first?
23. Volume packing ignores what real-world constraints?
24. How does pallet building cut freight cost?

**Dock Door Assignment** (`dock_door_assignment`)

25. Why group by destination?
26. More doors than destinations - assign freely or reserve?
27. What breaks good door plans?

**Cross-Dock Scheduling** (`cross_dock_scheduling`)

28. When does cross-docking beat storing?
29. What is the #1 operational failure mode?
30. Why start with FCFS scheduling?

Total: 30 questions.

## Part 2 - Answer key

1. Pick frequency (demand) - and often weight/size too, since heavy items also want easy spots.
2. At least seasonally - demand shifts silently turn your layout stale.
3. Cutting travel attacks most of the picking time; you cannot motivation your way out of a bad layout.
4. Travel time from pick face to packing/shipping - plus ergonomics: waist-height beats floor or ceiling.
5. Re-slot it forward immediately - waiting for the annual review costs travel every day.
6. Golden-zone space is scarce - the optimization's job is giving it to the items that earn it most.
7. Because pickers pay for the random choice every time - putaway errors tax every future pick.
8. A system decision instead of a forklift operator's guess - consistency, and slot data you can trust.
9. Rarely - e.g., to consolidate a product family or respect weight limits; the point is deciding consciously.
10. Efficiency (batching, less travel) vs responsiveness - late-arriving orders wait for the next release.
11. Waves must finish before each carrier leaves - the schedule is built backwards from the trucks.
12. When orders are tiny and urgent all day - continuous release keeps service snappier.
13. When an aisle has just one pick at its entrance - you still walk the whole aisle.
14. Return routing (go in and come back the same aisle) and midpoint routing (turn at half-aisle).
15. Pickers follow it without thinking, errors drop, and the distance gap to 'optimal' is usually small.
16. When picks sit near the aisle's near end - the far-end walk would be wasted distance.
17. Where along the aisle each pick sits - depth matters as much as which aisle.
18. Yes - smart pickers switch per aisle based on where the picks sit inside it.
19. Aisles constrain movement (you cannot walk through shelves) - coordinates must model the real walkable network.
20. Often similar distance, but S-shape wins on simplicity and consistency; TSP shines on small, spread-out picks.
21. True travel distances between locations (or a good aisle-graph model), not straight-line guesses.
22. Small items fit almost anywhere; big items fit almost nowhere - placing them first avoids stranded space.
23. Weight limits, stacking strength, fragility, and orientation - all matter before a pallet ships.
24. Fewer pallets per order can mean fewer trucks, or better use of a trailer's floor positions.
25. One destination per area means one staging lane, one pickup, no sorting errors at the last minute.
26. Reserve by flow: the busiest destinations earn the doors nearest shipping and staging.
27. Volume shifts by season - re-check assignments when destinations or volumes change materially.
28. When inbound and outbound flows match in time and content - the relay only works if the right outbound truck is there.
29. Waiting: inbound goods arrive with no outbound slot - then you are storing anyway, but badly.
30. It is fair, simple, and easy to audit - improve from a clean baseline, not from chaos.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
