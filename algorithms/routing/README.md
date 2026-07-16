---
title: "Routing & Transportation Algorithms | supplycm Algorithm Library"
description: "All 30 routing & transportation algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, routing, routing & transportation, supply chain algorithms"
---

# Routing & Transportation (30 algorithms)

Plan routes for trucks, deliveries, and service visits.

**Levels:** 2 beginner · 12 intermediate · 16 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [TSP Nearest Neighbor](tsp_nearest_neighbor.md) | Beginner | The instinctive route builder: from your start, always drive to the CLOSIST unvisited stop, repeat until done, then return home |
| 2 | [TSP 2-Opt Improvement](tsp_two_opt.md) | Beginner | Take any route and ask: would swapping two legs untangle a crossing? 2-opt removes two edges, reconnects the tour the better way, and repeats until no swap helps |
| 3 | [TSP 3-Opt Improvement](tsp_three_opt.md) | Advanced | 2-opt with a wider reach: cut THREE edges and try all smarter reconnections - including segment moves 2-opt can't express |
| 4 | [TSP Nearest Insertion](tsp_nearest_insertion.md) | Intermediate | Grow the tour like a snowball: start with two cities, then repeatedly grab the unvisited city CLOSEST to the current tour and insert it where it costs least |
| 5 | [TSP Cheapest Insertion](tsp_cheapest_insertion.md) | Intermediate | Insertion with a sharper eye: instead of choosing the city closest to the tour, choose the (city, gap) PAIR with the smallest insertion cost anywhere |
| 6 | [TSP Farthest Insertion](tsp_farthest_insertion.md) | Intermediate | The counterintuitive one: repeatedly insert the city FARTHEST from the tour, placing it in its cheapest gap |
| 7 | [TSP Held-Karp (Exact)](tsp_held_karp.md) | Advanced | The exact TSP algorithm: dynamic programming over subsets guarantees the optimal tour |
| 8 | [TSP Christofides Algorithm](tsp_christofides.md) | Advanced | The most beautiful guarantee in routing: build a minimum spanning tree, fix its odd-degree cities with a minimum matching, and turn the result into a tour |
| 9 | [Hungarian Algorithm (Assignment)](assignment_problem_hungarian.md) | Intermediate | N workers, N tasks, a cost for every pairing: find the one-to-one assignment with the MINIMUM total cost |
| 10 | [Northwest Corner Method](northwest_corner_method.md) | Intermediate | The simplest start for shipping plans: fill the top-left cell as much as possible, move right or down, repeat |
| 11 | [Least Cost Method](least_cost_method.md) | Intermediate | A smarter transportation start: allocate to the CHEAPEST available lane first, then the next cheapest, until supply meets demand |
| 12 | [Vogel's Approximation Method (VAM)](vogels_approximation.md) | Intermediate | The cleverest starting rule: for each row and column, compute the PENALTY of not using its cheapest lane (second-cheapest minus cheapest), then allocate wherever the penalty is highest |
| 13 | [MODI / Transportation Simplex](transportation_simplex_modi.md) | Advanced | The optimizer for shipping tables: from any feasible plan, compute hidden prices (MODI values) for each used lane, find a cell where shipping would SAVE money, shuffle quantities around a loop, and repeat until no cell offers savings |
| 14 | [Transshipment Problem](transshipment_problem.md) | Advanced | Real networks have middlemen: goods flow factory -> depot -> store, with depots neither producing nor consuming |
| 15 | [Vehicle Scheduling (Minimum Fleet)](vehicle_scheduling.md) | Advanced | How many vehicles does today's timetable actually need? Sort trips by start time and let each vehicle chain compatible trips back-to-back |
| 16 | [CVRP Greedy Insertion](vrp_capacitated_greedy.md) | Intermediate | The workhorse vehicle routing start: each vehicle leaves the depot and repeatedly grabs the nearest customer that fits its remaining capacity; when nothing fits, it comes home and a new vehicle starts |
| 17 | [Clarke-Wright Savings Algorithm](vrp_savings.md) | Intermediate | The classic CVRP builder with a beautiful idea: start with every customer on their own tiny out-and-back route, then MERGE pairs whenever merging saves distance - ranked by the 'savings' s(i,j) = cost(i,depot) + cost(depot,j) - cost(i,j) |
| 18 | [VRP Sweep Algorithm](vrp_sweep.md) | Intermediate | Stir the customer map like a clock hand from the depot: customers are swept into wedges, each wedge becomes one vehicle's route |
| 19 | [Cluster-First, Route-Second](vrp_cluster_first_route_second.md) | Intermediate | The two-phase strategy in its purest form: first GROUP customers into vehicle-sized clusters (geographically), then solve a TSP within each cluster |
| 20 | [Split Delivery VRP](split_delivery_vrp.md) | Advanced | Classic VRP forces each customer onto exactly ONE vehicle - but why? Allowing a customer's demand to be SPLIT across vehicles can serve everyone with fewer trucks and fewer kilometers |
| 21 | [VRP with Time Windows](vrp_with_time_windows.md) | Advanced | Customers demand service within windows - 'between 9 and 11' - and the route must arrive inside them, waiting if early |
| 22 | [Multi-Depot VRP](multi_depot_vrp.md) | Advanced | Several depots, one customer set: which depot serves whom, and in what order? This assigns customers to depots and builds routes - the two decisions that single-depot VRP never faced |
| 23 | [Periodic VRP](periodic_vrp.md) | Advanced | Some customers need visits on SCHEDULES - twice a week, say - but the exact days are your choice |
| 24 | [Pickup and Delivery Problem (PDP)](pickup_delivery_problem.md) | Advanced | Ride-sharing for freight: every request has a pickup AND a delivery stop, and the pickup MUST precede its delivery on the same route |
| 25 | [Dial-a-Ride](dial_a_ride.md) | Advanced | PDP with passengers: each request specifies pickup point, drop-off point, and how many ride - like patient transport or shared shuttles |
| 26 | [Eulerian Tour](eulerian_tour.md) | Intermediate | Walk every EDGE of a network exactly once and return to start - possible exactly when every node has an even number of connections |
| 27 | [Chinese Postman Problem](chinese_postman.md) | Advanced | Cover every street of a network at minimum total distance - repeating where necessary |
| 28 | [Rural Postman Problem](rural_postman.md) | Advanced | Only SOME streets need coverage - the required subset - while others are optional connectors |
| 29 | [Steiner Tree](steiner_tree.md) | Advanced | Connect a chosen set of terminals as cheaply as possible - possibly through NON-terminal junction points |
| 30 | [Hamiltonian Path (Backtracking)](hamiltonian_path_backtrack.md) | Advanced | Visit every node EXACTLY once - a path touching all stops with no repeats |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_routing.md](../../flashcards/flashcards_routing.md)
- Recall drill: [drills/drill_routing.md](../../drills/drill_routing.md)

## Choosing between the routing methods

- **One vehicle, quick route?** Nearest Neighbor, then improve with 2-Opt.
- **Want better than greedy without heavy machinery?** Cheapest Insertion.
- **Need the true optimum on a small stop set?** Held-Karp.
- **Several vehicles with capacity limits?** Clarke-Wright Savings or CVRP Greedy.
- **Time windows matter?** VRP with Time Windows.
- **Covering every street (not every stop)?** Chinese or Rural Postman.
