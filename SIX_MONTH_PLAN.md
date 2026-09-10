---
title: "The 6-Month Supply Chain Program | supplycm Learning"
description: "A week-by-week, 26-week program that takes a complete beginner to a highly capable supply chain professional using the supplycm package. No math beyond basic arithmetic."
keywords: "6 month plan, supply chain program, study schedule, learning path, supplycm, week by week"
---

# The 6-Month Supply Chain Program

> **26 weeks. 5-6 hours per week. Zero math beyond +, -, ×, ÷. One clear outcome: you finish as a highly capable supply chain professional who can forecast, buy, plan, route, and improve - with evidence.**

This is not a reading list. It is a training program. Every week has four moves:

| Move | What it means | Time |
|------|--------------|------|
| **Learn** | Read the core lesson and the algorithm pages listed | 2 h |
| **Practice** | Run the examples, do the drill, work the exercises | 2 h |
| **Recall** | Flashcards + the week's quiz, from memory, out loud | 1 h |
| **Apply** | Use it on YOUR business (or the running case study) | 1 h |

**The daily ritual (15 minutes, non-negotiable):** open your flashcard deck, review 10 cards, answer out loud, check. Memory is built by frequency, not by marathon sessions.

**The running case study:** From week 1 you will pick one small business - a cafe, a web shop, a workshop, anything real or realistic. Every month ends with you applying that month's skills to it. By week 26 you will have run a complete supply chain project on it, and your final capstone will simply assemble the work you have already done.

---

## Month 1 - Foundations: see the chain, measure the noise (Weeks 1-4)

**You leave this month able to: describe a supply chain, forecast a stable product honestly, and explain EOQ and safety stock to a manager.**

### Week 1 - What a supply chain actually is
- **Learn:** [Module 1: What is a Supply Chain?](modules/01_what_is_supply_chain.md) + notebook 01
- **Library pages:** start the [Statistics & Accuracy](algorithms/statistics/README.md) pages: Descriptive Stats, Z-Score, Coefficient of Variation, Min-Max Scaling
- **Practice:** run each example in the notebook; describe the 5 steps (Plan, Source, Make, Deliver, Return) of your case business in writing
- **Reinforce:** flashcards `statistics` (first 10 cards); [Quiz 1](quizzes/quiz_01_basics.md)
- **Apply:** map your case business's suppliers, process, customers, and one flow of goods on paper
- **Checkpoint:** you can define supply chain management in two sentences without notes

### Week 2 - Forecasting from zero
- **Learn:** [Module 2: Predicting the Future](modules/02_forecasting.md) + notebook 02
- **Library pages:** [Forecasting](algorithms/forecasting/README.md): Naive Forecast, Seasonal Naive, Average Method, Simple Moving Average, Weighted Moving Average
- **Practice:** [Exercise 2](exercises/exercise_02_forecasting.md); run all five methods on the same series and compare
- **Reinforce:** [Quiz 2](quizzes/quiz_02_forecasting.md); drill `statistics` part 1
- **Apply:** produce a 4-week forecast for your case business using a 3-week moving average
- **Checkpoint:** you can explain WHY the naive forecast is the fair benchmark

### Week 3 - Measuring whether you are any good
- **Learn:** error metrics: MAE, RMSE, MAPE, Bias, MASE, Forecast Value Added (Forecasting library)
- **Library pages:** MAE, MSE, RMSE, MAPE, Bias, MASE, FVA, Tracking Signal, Theil's U
- **Practice:** score your week-2 forecast three ways (MAE, MAPE, vs naive with MASE) and write which method won and why
- **Reinforce:** flashcards `forecasting` (basics batch); [Drill: statistics](drills/drill_statistics.md)
- **Apply:** build a tiny accuracy scorecard for your case business's top product
- **Checkpoint:** you can say "our forecast beats naive by X%" and defend it

### Week 4 - Inventory: the first big lever
- **Learn:** [Module 3: Inventory Management](modules/03_inventory.md) + notebook 03
- **Library pages:** [Inventory](algorithms/inventory/README.md): EOQ, Reorder Point, Safety Stock (Normal), Demand During Lead Time, Days of Supply, Inventory Position, ABC Analysis
- **Practice:** [Exercise 3](exercises/exercise_03_inventory.md); compute EOQ and ROP for three products of your case business
- **Reinforce:** [Quiz 3](quizzes/quiz_03_inventory.md); flashcards `inventory` (EOQ batch)
- **Apply:** set a written ordering rule (how much, when) for one real product
- **Checkpoint:** **MONTH 1 REVIEW** - you can explain forecasting, its accuracy, and EOQ+ROP to a friend in 10 minutes. Retake quizzes 1-3 until 90%.

## Month 2 - Forecasting in the wild: seasons, chaos, and confidence (Weeks 5-8)

**You leave this month able to forecast seasonal, trending, and intermittent products - and to communicate uncertainty honestly.**

### Week 5 - Smoothing engines
- **Learn:** SES, Holt, Damped Trend, Holt-Winters (Forecasting library)
- **Library pages:** Single Exponential Smoothing, Holt's Linear Trend, Dampened Trend, Holt-Winters, Brown's Double & Triple
- **Practice:** fit all of them to one seasonal series; make Holt-Winters your reference point
- **Reinforce:** flashcards `forecasting` (smoothing batch); [Recall drill: forecasting](drills/drill_forecasting.md)
- **Apply:** pick the best smoothing model for your case product - with evidence from MAE
- **Checkpoint:** you can sketch what alpha, beta, and gamma each control

### Week 6 - Seasonality and decomposition
- **Learn:** Classical Decomposition, STL, Seasonal Indices, MSTL (Forecasting library)
- **Library pages:** Seasonal Indices, Classical Decomposition, STL, MSTL, Demand: Seasonality Index, Trend-Seasonal Forecast
- **Practice:** decompose 24 months of a seasonal product; write the "story" of its trend and season
- **Reinforce:** [Quiz 2 retake](quizzes/quiz_02_forecasting.md) until 90%; flashcards `demand`
- **Apply:** compute monthly seasonal indices for your case business and annotate the calendar year
- **Checkpoint:** you can explain the December index to a shop owner in one sentence

### Week 7 - Messy demand: intermittent, spiky, and shifting
- **Learn:** Croston, SBA, TSB, Demand Sensing, Promotional Lift, Cannibalization (Forecasting + Demand libraries)
- **Library pages:** Croston's Method, SBA, TSB, Croston with Decay, Demand Sensing, Promotional Demand Lift, Cannibalization, Stockout Demand Loss
- **Practice:** forecast a spare part with 80% zero-days using Croston AND SBA; notice the bias gap
- **Reinforce:** [Drill: demand](drills/drill_demand.md); flashcards `forecasting` (intermittent batch)
- **Apply:** classify your case business's products into X/Y/Z and pick a method for each
- **Checkpoint:** you can explain why averaging zeros lies

### Week 8 - Honest numbers: intervals, tests, and statistical hygiene
- **Learn:** confidence intervals, normality checks, and model selection discipline (Statistics library)
- **Library pages:** Confidence Interval, Bootstrap CI, ADF & KPSS, Ljung-Box, AIC/BIC, Adjusted R-Squared, Bates-Granger Combination
- **Practice:** put an honest interval around one of your forecasts; run a Bates-Granger blend of your two best models
- **Reinforce:** [Quiz 1-3 spot retake](quizzes/README.md); flashcards `statistics` full deck once
- **Apply:** add "likely range" to your case business's monthly forecast
- **Checkpoint:** **MONTH 2 REVIEW** - your forecast file now has: method, error metrics, vs-naive comparison, and an honest range. That is a professional forecast.

## Month 3 - Inventory mastery and the purchasing brain (Weeks 9-13)

**You leave this month able to run a full inventory system: policies per item class, newsvendor decisions for one-shot buys, and supplier choices with evidence.**

### Week 9 - Policies: continuous vs periodic
- **Learn:** (R,Q), (s,S), Base-Stock, Periodic Review (Inventory library)
- **Library pages:** (R,Q) Policy, (s,S) Policy, Base-Stock Policy, Periodic Review Policy, Fill Rate, Cycle Service Level, Expected Backorder, Expected On-Hand
- **Practice:** implement (R,Q) and Periodic Review for two products; compare implied buffers
- **Reinforce:** flashcards `inventory` (policies batch); [Drill: inventory](drills/drill_inventory.md) part 1
- **Apply:** choose and document a policy per product class in your case business
- **Checkpoint:** you can explain why periodic review needs a bigger buffer

### Week 10 - When one shot is all you get: newsvendor thinking
- **Learn:** Newsvendor, Marginal Analysis, Perishable Ordering, Optimal Stockout Probability (Inventory library)
- **Library pages:** Newsvendor Model, Marginal Analysis Newsvendor, Perishable Inventory, Optimal Stockout Probability, Stockout Cost
- **Practice:** order a "season" of one product three ways and compare expected profits
- **Reinforce:** flashcards `inventory` (newsvendor batch)
- **Apply:** size one seasonal/promotional buy for your case business with the newsvendor logic
- **Checkpoint:** you can explain overage vs underage in one breath

### Week 11 - Inventory as money: metrics, valuation, and dead weight
- **Learn:** turnover, GMROI, aging, dead stock, FIFO/LIFO/WAC (Inventory library)
- **Library pages:** Inventory Turnover, Inventory-to-Sales, GMROI, Aging Schedule, Dead Stock, Slow Movers, Obsolescence Cost, FIFO, LIFO, Weighted Average Cost
- **Practice:** compute the full metric panel for your case business (invent the numbers if needed); flag 2 dead-stock candidates
- **Reinforce:** [Quiz 3 retake](quizzes/quiz_03_inventory.md); flashcards `inventory` (metrics batch)
- **Apply:** write a one-page "inventory health report" with three findings and three actions
- **Checkpoint:** you can explain why GMROI beats turnover alone

### Week 12 - Networks of stock: pooling, bullwhip, echelons
- **Learn:** Risk Pooling, Square Root Law, Bullwhip, Pipeline, Decoupling, Multi-Echelon (Inventory library)
- **Library pages:** Risk Pooling, Square Root Law, Bullwhip Effect, Pipeline Inventory, Anticipation Inventory, Decoupling Inventory, Multi-Echelon, Vendor Managed Inventory
- **Practice:** compute the stock impact of consolidating 4 stockrooms into 1; diagram the bullwhip in a 3-tier chain
- **Reinforce:** [Drill: inventory](drills/drill_inventory.md) part 2; flashcards `inventory` (network batch)
- **Apply:** estimate the pipeline inventory your case business currently has in transit
- **Checkpoint:** you can explain the bullwhip effect with a garden hose story

### Week 13 - Choosing suppliers like a professional
- **Learn:** Weighted Point, Scorecards, Kraljic, TCO, On-Time Delivery (Supplier library)
- **Library pages:** [Supplier](algorithms/supplier/README.md): Weighted Point Method, Evaluation Matrix, Vendor Scorecard, Supplier Rating, On-Time Delivery, Lead Time Quoted vs Actual, Supplier Segmentation (Kraljic), TCO, PPV
- **Practice:** score 3 suppliers on 4 criteria; place them in the Kraljic matrix; write a playbook per quadrant
- **Reinforce:** [Quiz 4](quizzes/quiz_04_suppliers.md); flashcards `supplier` (selection batch)
- **Apply:** run the weighted-point method for one real (or realistic) purchase decision
- **Checkpoint:** **MONTH 3 REVIEW** - you now have: item policies, a newsvendor decision, an inventory health report, and a supplier selection file. This is a buyer's toolkit.

## Month 4 - The planning engine: MRP, S&OP, schedules, flow, quality (Weeks 14-17)

**You leave this month able to plan production end-to-end and defend the schedule on the floor.**

### Week 14 - From orders to purchase orders: MRP mechanics
- **Learn:** BOM explosion, low-level coding, MRP records, lot sizing rules (MRP library)
- **Library pages:** [MRP](algorithms/mrp/README.md): BOM Explosion, Where-Used, Low-Level Coding, MRP Calculation, Lead Time Offsetting, L4L, FOQ, POQ, Silver-Meal, Minimum Order Quantity, Order Multiples, Shrinkage
- **Practice:** explode a 3-level BOM for demand 100; run the MRP calculation with two lot-size rules and compare costs
- **Reinforce:** flashcards `mrp` (BOM batch); [Drill: MRP](drills/drill_mrp.md) part 1
- **Apply:** build a mini BOM for your case product and explode it by hand, then verify
- **Checkpoint:** you can draw the four MRP rows from memory

### Week 15 - Promises: MPS, ATP, fences, and capacity
- **Learn:** MPS, ATP/CTP, time fences, RCCP/CRP, DBR, Kanban (MRP library)
- **Library pages:** Master Production Schedule, Available-to-Promise, Capable-to-Promise, Demand Time Fence, Planning Time Fence, RCCP, CRP, Drum-Buffer-Rope, Kanban Sizing, Cycle Counting
- **Practice:** build an MPS with real orders consuming forecast; find what ATP lets sales promise in week 2
- **Reinforce:** [Quiz 9](quizzes/quiz_09_sop.md); flashcards `mrp` (planning batch)
- **Apply:** write the promise rules (fences, ATP policy) for your case business on one page
- **Checkpoint:** you can explain why sales and planning fight, and how fences make peace

### Week 16 - S&OP and the shape of production
- **Learn:** chase vs level, demand-supply matching (S&OP library) + scheduling rules (Scheduling library)
- **Library pages:** [S&OP](algorithms/sop/README.md) all three; [Scheduling](algorithms/scheduling/README.md): FCFS, SPT, WSPT, EDD, Critical Ratio, Tardiness, Total Completion Time
- **Practice:** build chase and level plans for a seasonal demand series; compare their costs by hand
- **Reinforce:** [Drill: scheduling](drills/drill_scheduling.md) part 1; flashcards `sop`
- **Apply:** write the S&OP calendar (who meets, when, what inputs) for your case business
- **Checkpoint:** you can defend a hybrid strategy in a mock meeting

### Week 17 - Flow and quality: lean metrics that don't lie
- **Learn:** takt, OEE, Little's Law, PCE + Six Sigma scoreboard (Lean + Quality libraries)
- **Library pages:** [Lean](algorithms/lean/README.md) all four; [Quality](algorithms/quality/README.md): DPMO, Sigma Level, Cp, Cpk, X-bar & R charts, P chart
- **Practice:** compute takt for a known demand; build an X-bar chart from invented samples and catch the drift
- **Reinforce:** [Quiz 7 + 8](quizzes/quiz_07_quality.md); flashcards `lean` + `quality`
- **Apply:** measure one process in your case business: cycle time efficiency + DPMO, and name one improvement
- **Checkpoint:** **MONTH 4 REVIEW** - mid-program checkpoint: retake ALL quizzes 1-9; you should average 85%+. Your case file now has plans, promises, and measurements.

## Month 5 - Moving goods: routing, networks, warehouses (Weeks 18-22)

**You leave this month able to design routes and networks and lay out a warehouse that doesn't waste steps.**

### Week 18 - Routes: TSP from greedy to good
- **Learn:** nearest neighbor, 2-opt, insertion heuristics, Held-Karp as truth (Routing library)
- **Library pages:** [Routing](algorithms/routing/README.md): TSP Nearest Neighbor, 2-Opt, 3-Opt, Nearest/Cheapest/Farthest Insertion, Held-Karp, Christofides
- **Practice:** build a 8-stop route with NN, fix it with 2-opt, and measure against Held-Karp truth on a 8-stop subset
- **Reinforce:** [Quiz 6](quizzes/quiz_06_transportation.md); flashcards `routing` (TSP batch)
- **Apply:** plan a real delivery/pickup round for your case business and report the % saved vs your first attempt
- **Checkpoint:** you can explain why greedy routes cross themselves

### Week 19 - Many vehicles: VRP family
- **Learn:** CVRP greedy, Clarke-Wright savings, sweep, time windows (Routing library)
- **Library pages:** CVRP Greedy, VRP Savings, VRP Sweep, Cluster-First-Route-Second, VRP with Time Windows, Split Delivery, Multi-Depot
- **Practice:** solve one CVRP three ways (greedy, savings, sweep) and compare total distance
- **Reinforce:** [Drill: routing](drills/drill_routing.md); flashcards `routing` (VRP batch)
- **Apply:** plan a two-vehicle day for your case business with capacity logic
- **Checkpoint:** you can explain the savings formula in words

### Week 20 - Networks: paths, hubs, and weak points
- **Learn:** BFS/DFS, Dijkstra, A*, MST, max flow, min cut (Network library)
- **Library pages:** [Network](algorithms/network/README.md): BFS, DFS, Dijkstra, A*, Bellman-Ford, Floyd-Warshall, Kruskal, Prim, Max Flow, Min-Cut Theorem
- **Practice:** find cheapest paths on a hand-drawn lane network; find the bottleneck cut and defend one investment
- **Reinforce:** flashcards `network` (paths batch); [Drill: networks](drills/drill_network.md)
- **Apply:** model your case business's supply lanes and locate its single point of failure
- **Checkpoint:** you can explain "max flow = min cut" to a manager

### Week 21 - Warehouse physics: slotting and picking
- **Learn:** ABC slotting, S-shape and return routing, waves, pallets (Warehouse library)
- **Library pages:** [Warehouse](algorithms/warehouse/README.md) all ten pages; Routing: Chinese Postman (for edge-coverage work)
- **Practice:** slot 8 items into zones; compare S-shape vs return routing distances on one pick list
- **Reinforce:** [Quiz 5](quizzes/quiz_05_warehouses.md); flashcards `warehouse`
- **Apply:** design (on paper) the pick path for your case business's storeroom
- **Checkpoint:** you can explain why the milk is NOT at the back of the warehouse

### Week 22 - Where to put the building: network design
- **Learn:** center of gravity, facility location, break-even, allocation (Network Design library)
- **Library pages:** [Network Design](algorithms/network_design/README.md) all five; Network: [Closeness Centrality](algorithms/network/closeness_centrality.md) and [Betweenness Centrality](algorithms/network/betweenness_centrality.md)
- **Practice:** site a DC with center of gravity, then score the candidates with facility location logic
- **Reinforce:** flashcards `network_design`; [Drill: networks](drills/drill_network.md) part 2
- **Apply:** write a one-page siting recommendation for your case business with evidence
- **Checkpoint:** **MONTH 5 REVIEW** - retake quizzes 4-6; your case file now includes routes, a network map, and a warehouse plan.

## Month 6 - Modern edges and the capstone (Weeks 23-26)

**You leave this program with a complete portfolio: optimization, modern tech, contracts, sustainability - and a finished supply chain project.**

### Week 23 - Optimization thinking: the classic toolkit
- **Learn:** knapsacks, bin packing, set cover, greedy vs DP, metaheuristics (Optimization library)
- **Library pages:** [Optimization](algorithms/optimization/README.md): Fractional Knapsack, 0-1 Knapsack, Bin Packing (all three), Set Cover, Golden Section, Gradient Descent, Simulated Annealing, Tabu, GA, PSO (skim the last four)
- **Practice:** pack a truck two ways (first-fit vs FFD); feel why sorting matters
- **Reinforce:** flashcards `optimization` (first half); [Drill: optimization](drills/drill_optimization.md)
- **Apply:** find one hidden optimization problem in your case business and name its type
- **Checkpoint:** you can classify a problem as knapsack/covering/routing in one look

### Week 24 - The modern supply chain: sensors, traces, simulations
- **Learn:** IoT monitoring, traceability, Monte Carlo (IoT + Blockchain + Simulation libraries)
- **Library pages:** [IoT](algorithms/iot/README.md) all four; [Blockchain](algorithms/blockchain/README.md) all four; [Simulation](algorithms/simulation/README.md) both
- **Practice:** run a Monte Carlo inventory simulation; build a hash chain and break it on purpose
- **Reinforce:** flashcards `iot` + `blockchain`; [Quiz 12 spot check](quizzes/quiz_12_final.md)
- **Apply:** write a one-page tech adoption memo: what would you instrument and trace at your case business, and why
- **Checkpoint:** you can explain "tamper-evident" without the word blockchain

### Week 25 - Deals, risk, and green: the executive layer
- **Learn:** contracts, resilience index, carbon and returns (Contracts + Risk + Sustainability libraries) + advanced supplier methods (Supplier library part B)
- **Library pages:** [Contracts](algorithms/contracts/README.md) all three; [Risk](algorithms/risk/README.md); [Sustainability](algorithms/sustainability/README.md) all three; Supplier: TOPSIS, AHP, Should-Cost, DEA; Cost: Landed Cost, Total Procurement Cost
- **Practice:** model a buyback contract at two demand levels; compute a landed cost that changes a sourcing decision
- **Reinforce:** [Quiz 10 + 11](quizzes/quiz_10_contracts.md); flashcards `contracts` + `sustainability`
- **Apply:** add a carbon line and a contract clause to your case business's biggest purchase
- **Checkpoint:** you can argue a sourcing decision on total cost, risk, AND carbon

### Week 26 - Capstone and graduation
- **Assemble:** compile your 6 months of case-business work into one project document:
  1. demand forecast with accuracy evidence (Month 2)
  2. inventory policies and health report (Month 3)
  3. supplier selection and a purchase plan (Month 3)
  4. S&OP calendar and MPS with promise rules (Month 4)
  5. process measurements and one improvement (Month 4)
  6. routes, network map, warehouse layout (Month 5)
  7. tech memo, contract and carbon note (Month 6)
- **Learn:** [Module 12: Putting It All Together](modules/12_putting_it_together.md) - compare your approach with the worked example
- **Exam:** [Final Quiz](quizzes/quiz_12_final.md) - target 85%+
- **Celebrate:** update your [Algorithm Progress Tracker](progress/ALGORITHM_TRACKER.md) one last time and count what you can now explain
- **Checkpoint:** **GRADUATION.** You can walk into a supply chain role and add value in week one.

---

## Rules of the program

1. **Never skip the recall step.** Reading feels like learning; recall IS learning. 15 minutes daily beats 3 hours on Sunday.
2. **When stuck on a page, run the code.** Every example in the library runs as printed. Change one number, re-run, watch what moves. That loop teaches faster than re-reading.
3. **One business, six months.** The running case study is what turns knowledge into capability. Do not switch businesses halfway.
4. **Falling behind?** Compress, don't skip: do the Learn + Apply moves and defer the extra Practice items to the review week. Never skip a checkpoint.
5. **Ahead of schedule?** Go deeper in the library - every module page ends with a "Try this now" challenge that has no upper bound.
6. **No math beyond +, -, ×, ÷.** If a page seems to need more, the fault is ours - [open an issue](https://github.com/atqatq/supplycm-learning/issues).

## Where the hours go (per week, typical)

| Activity | Hours |
|----------|-------|
| Reading lessons + library pages | 2.0 |
| Running code + exercises | 2.0 |
| Flashcards + drills + quizzes | 1.0 |
| Applying to your case business | 0.5-1.0 |
| **Total** | **5.5** |

## After graduation

- Keep the daily 15-minute recall ritual for one more month - it protects everything you built.
- Take one library module per week and do every "Try this now" challenge with real data.
- Teach: write one explanation per week in [Discussions](https://github.com/atqatq/supplycm-learning/discussions). Teaching is the final level of learning.
- Then read the [FAQ](FAQ.md) for what to learn next, and star the [supplycm package](https://github.com/atqatq/supplycm) - new algorithms arrive regularly, and now you can read them like a professional.
