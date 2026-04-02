---
title: "Recall Drill: Routing & Transportation | supplycm Learning"
description: "Active-recall drill with answer key covering all 30 supplycm routing & transportation algorithms."
keywords: "drill, recall, routing, supply chain practice"
---

# Recall Drill: Routing & Transportation

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**TSP Nearest Neighbor** (`tsp_nearest_neighbor`)

1. Why can nearest neighbor paint itself into a corner?
2. Does the start city change the result?
3. Why keep it as a benchmark?

**TSP 2-Opt Improvement** (`tsp_two_opt`)

4. What swap does 2-opt perform?
5. Why do crossing edges signal improvement available?
6. 2-opt's weakness?

**TSP 3-Opt Improvement** (`tsp_three_opt`)

7. What can 3-opt do that 2-opt can't?
8. Why not always run 3-opt?
9. How do you escape 3-opt's local optimum?

**TSP Nearest Insertion** (`tsp_nearest_insertion`)

10. How does insertion differ from nearest-neighbor construction?
11. Why does 'cheapest insertion point' matter?
12. What comes after insertion heuristics?

**TSP Cheapest Insertion** (`tsp_cheapest_insertion`)

13. Nearest vs cheapest insertion - the precise difference?
14. Why is cheapest usually better?
15. What do both share with all insertion methods?

**TSP Farthest Insertion** (`tsp_farthest_insertion`)

16. Why would FARTHEST first help?
17. When does farthest insertion shine?
18. Is any insertion rule universally best?

**TSP Held-Karp (Exact)** (`tsp_held_karp`)

19. Why can't Held-Karp scale to 100 stops?
20. What is it actually FOR, then?
21. What runs on big instances in practice?

**TSP Christofides Algorithm** (`tsp_christofides`)

22. What is the 1.5x guarantee?
23. Why does the spanning tree start the construction?
24. What breaks the guarantee?

**Hungarian Algorithm (Assignment)** (`assignment_problem_hungarian`)

25. What kind of problems does Hungarian solve exactly?
26. What if a worker can take TWO tasks?
27. Where does the matrix come from in practice?

**Northwest Corner Method** (`northwest_corner_method`)

28. Why use a method that ignores costs?
29. What are supply and demand here?
30. What comes immediately after?

**Least Cost Method** (`least_cost_method`)

31. How much better is least-cost vs northwest corner?
32. Can the greedy start still be beaten?
33. When is the starting method irrelevant?

**Vogel's Approximation Method (VAM)** (`vogels_approximation`)

34. What does the penalty (opportunity cost) capture?
35. Why is VAM often the best start?
36. Do better starts matter if MODI optimizes anyway?

**MODI / Transportation Simplex** (`transportation_simplex_modi`)

37. What do MODI values (u, v) actually measure?
38. What is a 'loop' in the improvement step?
39. When does the algorithm stop?

**Transshipment Problem** (`transshipment_problem`)

40. What distinguishes a transshipment node?
41. Why can a two-hop route beat a direct one?
42. How does this relate to min-cost flow?

**Vehicle Scheduling (Minimum Fleet)** (`vehicle_scheduling`)

43. What determines whether two trips can share a vehicle?
44. Why is this deceptively simple here?
45. What does each extra vehicle cost you?

**CVRP Greedy Insertion** (`vrp_capacitated_greedy`)

46. What does 'capacitated' add over plain TSP?
47. Why does greedy leave money on the table?
48. What's the first polish to apply?

**Clarke-Wright Savings Algorithm** (`vrp_savings`)

49. What exactly is a 'saving'?
50. Why does merging start from single-customer routes?
51. What constrains a merge?

**VRP Sweep Algorithm** (`vrp_sweep`)

52. What does the sweep angle decide?
53. When does sweep clustering mislead?
54. How do you pick the number of wedges?

**Cluster-First, Route-Second** (`vrp_cluster_first_route_second`)

55. What's the alternative to cluster-first-route-second?
56. Where does clustering fail the route?
57. How would you repair boundary mistakes?

**Split Delivery VRP** (`split_delivery_vrp`)

58. Why does splitting reduce vehicle count?
59. What's the operational cost of splitting?
60. When is splitting most valuable?

**VRP with Time Windows** (`vrp_with_time_windows`)

61. What new tension do time windows add?
62. Why do vehicles proliferate under tight windows?
63. What should you negotiate first when infeasible?

**Multi-Depot VRP** (`multi_depot_vrp`)

64. What does the depot assignment decision trade off?
65. How does this interact with network design?
66. What's the classic failure mode?

**Periodic VRP** (`periodic_vrp`)

67. What two decisions does periodic VRP add?
68. Why does pattern choice matter so much?
69. What does flexibility in patterns buy?

**Pickup and Delivery Problem (PDP)** (`pickup_delivery_problem`)

70. What constraint defines a PDP route?
71. How does load tracking change?
72. Where do backhauls fit in?

**Dial-a-Ride** (`dial_a_ride`)

73. What do human passengers add over freight?
74. What is 'ride time' and why bound it?
75. How does capacity interact with pairs?

**Eulerian Tour** (`eulerian_tour`)

76. What does 'even degree' guarantee?
77. How does this differ from the TSP?
78. What if the graph has odd-degree nodes?

**Chinese Postman Problem** (`chinese_postman`)

79. When does the postman need to repeat streets?
80. How are odd nodes 'fixed'?
81. Why 'Chinese' postman?

**Rural Postman Problem** (`rural_postman`)

82. What makes rural postman harder than Chinese postman?
83. When does it collapse to the Chinese Postman?
84. How would you model 'grit only priority roads'?

**Steiner Tree** (`steiner_tree`)

85. Steiner tree vs MST - what's the essential difference?
86. Why would a non-terminal node help?
87. What's the computational catch?

**Hamiltonian Path (Backtracking)** (`hamiltonian_path_backtrack`)

88. Hamiltonian path vs Eulerian tour - what's the difference?
89. Why is this problem so hard computationally?
90. Where does it appear in logistics?

Total: 90 questions.

## Part 2 - Answer key

1. Greedy closeness ignores the return trip - early cheap hops can force one horrific final leg.
2. Often, substantially - try each start on small problems; the best NN route is the best of those attempts.
3. It is free and instant - any fancier method must beat THIS to justify existing.
4. Delete two edges, reconnect the two resulting paths the opposite way - reversing the segment between the cut points.
5. Triangle inequality: uncrossed shortcuts always exist - crossings are visible proof of wasted distance.
6. It gets trapped in local optima - no single swap helps anymore, but a bigger rearrangement might; that's where 3-opt and metaheuristics enter.
7. Reconnect three cut pieces in genuinely different ORDERS - relocating segments, not just uncrossing them.
8. It explores many more reconnection cases per move - the cost shows on large routes and time-pressured dispatch.
9. Random restarts, perturbation (ruin-and-recreate), or metaheuristics - accept moves that temporarily worsen.
10. NN extends a PATH hop by hop; insertion keeps a valid closed TOUR and grows it - never leaving loose ends.
11. The same city can join anywhere - slotting it into its least-disruptive gap preserves the tour's economy.
12. Improvement: 2-opt/3-opt polish - construction gives a good skeleton; improvement trims the fat.
13. Nearest picks by CITY proximity to the tour; cheapest scans all (city, position) pairs by insertion COST.
14. It evaluates the actual increment - a nearby city might only fit badly, while a slightly farther one slots in for pennies.
15. They maintain valid complete tours at every step - you could stop mid-way and still have a usable route.
16. Distant cities constrain the tour's shape most - fixing their placement early prevents costly detours later.
17. Clustered stops with far outliers - the outliers define the tour's rough outline instantly.
18. No - instance-dependent; that's why pipelines try several seeds and keep the best after improvement.
19. It stores best costs for every (subset, endpoint) pair - 2^n subsets explode past n = 20-ish into memory oblivion.
20. Truth on small cases: knowing the optimal answer tells you your heuristic is 4% or 40% off - calibration.
21. Heuristics and metaheuristics (Lin-Kernighan style), which routinely land within a percent or two of optimal.
22. Tour length at most 1.5 times optimal - proven, always, when distances obey the triangle inequality.
23. It's the cheapest skeleton connecting everyone - Christofides then patches the skeleton into a full loop cheaply.
24. Non-metric distances - if the triangle inequality fails, the proof's floor falls away too.
25. Square one-to-one assignments - optimal, not heuristic, in fast polynomial time.
26. Duplicate the worker's row - capacity 2 becomes two identical rows; the math absorbs it happily.
27. Time-and-motion data or fit scores - the algorithm is only as honest as the costs you feed it.
28. Speed to a FEASIBLE plan - the starting point's quality matters less than having one to optimize.
29. Warehouse capacities and customer requirements - the plan must drain supply into demand exactly.
30. Cost improvement (MODI / stepping-stone) - the draft's dumb allocations get traded toward cheap lanes.
31. Usually substantially - greedy-on-cost starts near-optimal on easy instances, saving improvement iterations.
32. Easily - filling one cheap lane can strand an expensive corner; optimizers exist precisely because greed misleads.
33. When MODI runs to full optimality anyway - the endpoint is identical, only the journey differs.
34. How much you lose by missing a lane's cheap rate - high-penalty rows get served first to avoid that regret.
35. It looks one decision ahead - greed on penalties beats plain greed on costs in most instances.
36. Fewer iterations to optimality - and in big or degenerate problems, that difference is very real.
37. Implicit prices per origin and destination - their difference reveals each lane's true economic attractiveness.
38. The closed rectangle path that shifts quantities: add here, subtract there, keeping every row and column balanced.
39. When no empty cell has a negative improvement index - provably no cheaper allocation exists.
40. Pure pass-through: inflow equals outflow - it adds routing options, not supply or demand.
41. Economies, lane quality, or the direct lane being impossibly expensive - the model prices every option fairly.
42. It IS a min-cost flow with node balances - transshipment is the supply chain dialect of the same mathematics.
43. Non-overlap: the next trip starts at or after the previous one ends (plus deadhead travel, in richer models).
44. With pure time intervals, sorting suffices - real fleets add start/end depots and deadhead times, which complicate chaining.
45. Capital, driver, insurance, parking - the minimum-fleet answer converts directly into budget conversations.
46. Vehicles max out and return - the question splits from 'best tour' to 'best SET of tours under weight limits'.
47. It ignores route SHAPE and future customers - short-sighted grabs force long detours; improvement passes recover most of it.
48. Intra-route 2-opt per vehicle, then inter-route customer swaps - the standard one-two of VRP improvement.
49. The distance NOT driven by joining i and j directly instead of both via the depot - the win from carpooling, numerically.
50. Because every route must eventually connect to the depot - starting fragmented makes every possible merge available.
51. Vehicle capacity and route-compatibility (i at the end of one route, j at the front of another) - savings you can't legally realize are skipped.
52. Cluster membership - customers within a wedge travel together; bad angles split natural neighbors across routes.
53. When distance isn't angular - customers at similar angles but very different radii get lumped despite being far apart.
54. Total demand divided by vehicle capacity, adjusted for geography - then let the routing math judge the result.
55. Route-first-cluster-second: build one giant tour, then split it into vehicle trips at depot returns.
56. Boundary customers - the wedge line puts a customer in cluster A while their best insertion is in B; interfaces leak efficiency.
57. Inter-route exchanges after routing - move a customer between clusters when the total drops; iteration fixes division errors.
58. It eliminates stranded capacity - trucks no longer return half-full just because one customer 'belonged' elsewhere.
59. Extra stops at the same address, split paperwork, and customer confusion - model the benefit against the friction.
60. When demands hover near capacity - the awkward remainders that force extra vehicles vanish when division is allowed.
61. Distance wants compact routes; windows dictate order - the shortest-feeling route can violate a promise, and vice versa.
62. Feasibility, not capacity, binds: when 'by 10am' crowds the morning, extra vehicles buy time slots, not weight.
63. Window widths - widening one window by an hour often saves a whole vehicle; that's the highest-leverage phone call.
64. Distance to customers versus depot workload balance - nearest isn't always right when capacities strain.
65. It's the tactical twin: strategic siting chooses depots; this assigns flows daily - the layers nest.
66. Territory drawn by geography alone ignores demand volume - one depot drowns while its neighbor idles; balance assignments, not just maps.
67. Pattern assignment (which days per customer) and daily routing - they interact and must be planned together.
68. Serving all Monday-heavy patterns together drowns that day - spreading patterns smooths daily load like slotting smooths waves.
69. Leveling: customers who accept 'any two days' become shock absorbers - the planner's secret weapon.
70. Pairing precedence: for every request, pickup before delivery, same vehicle - everything else is negotiation.
71. Capacity now fluctuates stop by stop - goods ride along between their pickup and delivery, so the peak load matters, not the total.
72. As paired requests where the 'pickup' is a return at a delivery customer - one route serves both directions of commerce.
73. Service expectations - ride-time limits, punctuality, and dignity constraints that pure cargo never complains about.
74. Minutes between a passenger's pickup and drop-off - unbounded, a cheap route tours the city with someone aboard; bounded, routes stay humane.
75. Load rises at pickups, falls at drop-offs - the vehicle's peak onboard count, not total demand, must fit.
76. A closed tour using every edge once exists - the Euler condition; one odd node and it's impossible without duplication.
77. TSP minimizes visiting NODES; Eulerian tours cover EDGES exactly once - different object, different problem.
78. Some edges must be traversed twice - the Chinese Postman Problem computes the cheapest way to add those repeats.
79. When odd-degree nodes exist - pairing them with cheapest detours restores the even structure repeats buy.
80. Minimum-weight matching pairs them up; each pair's connecting path gets duplicated - the cheapest legal patch.
81. Named for the 1962 paper by Chinese mathematician Mei-Ko Kwan studying a postman's route in Beijing - mathematics remembering its origins.
82. Choosing WHICH optional edges to use is part of the problem - it bundles a design decision into the route.
83. When ALL edges are required - no selection remains, and the classic algorithm applies.
84. Priority roads = required edges; everything else = optional zero-obligation connectors - exactly this problem's inputs.
85. MST must connect ALL nodes; Steiner connects only terminals and CHOOSES helpful intermediates - freedom that buys savings.
86. It can act as a cheap junction - three roads meeting at one point often cost less than pairwise connections.
87. Choosing intermediates is NP-hard - real instances rely on heuristics; small ones get exact answers.
88. Nodes vs edges: Hamiltonian visits each NODE once; Eulerian covers each EDGE once - one is hard, the other easy to detect.
89. No known efficient general test - existence questions multiply combinatorially, and the best methods still explore in the worst case.
90. Sequential tour puzzles - one visit per stop with strict uniqueness - though practice usually relaxes to optimization versions.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
