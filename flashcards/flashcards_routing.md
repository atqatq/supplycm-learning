---
title: "Flashcards: Routing & Transportation | supplycm Learning"
description: "Spaced-repetition flashcards for all 30 supplycm routing & transportation algorithms."
keywords: "flashcards, routing, supply chain, recall"
---

# Flashcards: Routing & Transportation

30 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `tsp_nearest_neighbor` do? | TSP Nearest Neighbor: The instinctive route builder: from your start, always drive to the CLOSIST unvisited stop, repeat until done, then return home. |
| 2 | What does `tsp_two_opt` do? | TSP 2-Opt Improvement: Take any route and ask: would swapping two legs untangle a crossing? 2-opt removes two edges, reconnects the tour the better way, and repeats until no swap helps. |
| 3 | What does `tsp_three_opt` do? | TSP 3-Opt Improvement: 2-opt with a wider reach: cut THREE edges and try all smarter reconnections - including segment moves 2-opt can't express. |
| 4 | What does `tsp_nearest_insertion` do? | TSP Nearest Insertion: Grow the tour like a snowball: start with two cities, then repeatedly grab the unvisited city CLOSEST to the current tour and insert it where it costs least. |
| 5 | What does `tsp_cheapest_insertion` do? | TSP Cheapest Insertion: Insertion with a sharper eye: instead of choosing the city closest to the tour, choose the (city, gap) PAIR with the smallest insertion cost anywhere. |
| 6 | What does `tsp_farthest_insertion` do? | TSP Farthest Insertion: The counterintuitive one: repeatedly insert the city FARTHEST from the tour, placing it in its cheapest gap. |
| 7 | What does `tsp_held_karp` do? | TSP Held-Karp (Exact): The exact TSP algorithm: dynamic programming over subsets guarantees the optimal tour. |
| 8 | What does `tsp_christofides` do? | TSP Christofides Algorithm: The most beautiful guarantee in routing: build a minimum spanning tree, fix its odd-degree cities with a minimum matching, and turn the result into a tour. |
| 9 | What does `assignment_problem_hungarian` do? | Hungarian Algorithm (Assignment): N workers, N tasks, a cost for every pairing: find the one-to-one assignment with the MINIMUM total cost. |
| 10 | What does `northwest_corner_method` do? | Northwest Corner Method: The simplest start for shipping plans: fill the top-left cell as much as possible, move right or down, repeat. |
| 11 | What does `least_cost_method` do? | Least Cost Method: A smarter transportation start: allocate to the CHEAPEST available lane first, then the next cheapest, until supply meets demand. |
| 12 | What does `vogels_approximation` do? | Vogel's Approximation Method (VAM): The cleverest starting rule: for each row and column, compute the PENALTY of not using its cheapest lane (second-cheapest minus cheapest), then allocate wherever the penalty is highest. |
| 13 | What does `transportation_simplex_modi` do? | MODI / Transportation Simplex: The optimizer for shipping tables: from any feasible plan, compute hidden prices (MODI values) for each used lane, find a cell where shipping would SAVE money, shuffle quantities around a loop, and repeat until no cell offers savings. |
| 14 | What does `transshipment_problem` do? | Transshipment Problem: Real networks have middlemen: goods flow factory -> depot -> store, with depots neither producing nor consuming. |
| 15 | What does `vehicle_scheduling` do? | Vehicle Scheduling (Minimum Fleet): How many vehicles does today's timetable actually need? Sort trips by start time and let each vehicle chain compatible trips back-to-back. |
| 16 | What does `vrp_capacitated_greedy` do? | CVRP Greedy Insertion: The workhorse vehicle routing start: each vehicle leaves the depot and repeatedly grabs the nearest customer that fits its remaining capacity; when nothing fits, it comes home and a new vehicle starts. |
| 17 | What does `vrp_savings` do? | Clarke-Wright Savings Algorithm: The classic CVRP builder with a beautiful idea: start with every customer on their own tiny out-and-back route, then MERGE pairs whenever merging saves distance - ranked by the 'savings' s(i,j) = cost(i,depot) + cost(depot,j) - cost(i,j). |
| 18 | What does `vrp_sweep` do? | VRP Sweep Algorithm: Stir the customer map like a clock hand from the depot: customers are swept into wedges, each wedge becomes one vehicle's route. |
| 19 | What does `vrp_cluster_first_route_second` do? | Cluster-First, Route-Second: The two-phase strategy in its purest form: first GROUP customers into vehicle-sized clusters (geographically), then solve a TSP within each cluster. |
| 20 | What does `split_delivery_vrp` do? | Split Delivery VRP: Classic VRP forces each customer onto exactly ONE vehicle - but why? Allowing a customer's demand to be SPLIT across vehicles can serve everyone with fewer trucks and fewer kilometers. |
| 21 | What does `vrp_with_time_windows` do? | VRP with Time Windows: Customers demand service within windows - 'between 9 and 11' - and the route must arrive inside them, waiting if early. |
| 22 | What does `multi_depot_vrp` do? | Multi-Depot VRP: Several depots, one customer set: which depot serves whom, and in what order? This assigns customers to depots and builds routes - the two decisions that single-depot VRP never faced. |
| 23 | What does `periodic_vrp` do? | Periodic VRP: Some customers need visits on SCHEDULES - twice a week, say - but the exact days are your choice. |
| 24 | What does `pickup_delivery_problem` do? | Pickup and Delivery Problem (PDP): Ride-sharing for freight: every request has a pickup AND a delivery stop, and the pickup MUST precede its delivery on the same route. |
| 25 | What does `dial_a_ride` do? | Dial-a-Ride: PDP with passengers: each request specifies pickup point, drop-off point, and how many ride - like patient transport or shared shuttles. |
| 26 | What does `eulerian_tour` do? | Eulerian Tour: Walk every EDGE of a network exactly once and return to start - possible exactly when every node has an even number of connections. |
| 27 | What does `chinese_postman` do? | Chinese Postman Problem: Cover every street of a network at minimum total distance - repeating where necessary. |
| 28 | What does `rural_postman` do? | Rural Postman Problem: Only SOME streets need coverage - the required subset - while others are optional connectors. |
| 29 | What does `steiner_tree` do? | Steiner Tree: Connect a chosen set of terminals as cheaply as possible - possibly through NON-terminal junction points. |
| 30 | What does `hamiltonian_path_backtrack` do? | Hamiltonian Path (Backtracking): Visit every node EXACTLY once - a path touching all stops with no repeats. |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
