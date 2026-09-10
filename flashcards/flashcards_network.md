---
title: "Flashcards: Networks | supplycm Learning"
description: "Spaced-repetition flashcards for all 30 supplycm networks algorithms."
keywords: "flashcards, network, supply chain, recall"
---

# Flashcards: Networks

30 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `bfs_shortest_path` do? | BFS Shortest Path: Breadth-first search explores a network in rings: all direct neighbors, then neighbors-of-neighbors. |
| 2 | What does `dfs_traversal` do? | DFS Traversal: Depth-first search dives deep: follow one path as far as it goes, backtrack, try the next. |
| 3 | What does `bidirectional_search` do? | Bidirectional Search: Search from BOTH ends at once: BFS forward from the start and backward from the target, until the waves meet in the middle. |
| 4 | What does `dijkstra_shortest_path` do? | Dijkstra's Shortest Path: The workhorse of weighted routing: from the start, always expand the CHEAPEST known node next, updating neighbors' best distances. |
| 5 | What does `a_star_search` do? | A* Search: Dijkstra with a hunch: A* adds a heuristic - an estimate of remaining distance to the goal - and explores in the direction of promise. |
| 6 | What does `bellman_ford` do? | Bellman-Ford: The careful shortest-path algorithm: relax every edge repeatedly, and even NEGATIVE costs are handled correctly. |
| 7 | What does `all_pairs_shortest_path` do? | All-Pairs Shortest Path: Instead of one origin, run shortest paths between EVERY pair of nodes in one structured pass. |
| 8 | What does `floyd_warshall` do? | Floyd-Warshall: The elegant all-pairs algorithm: consider each node in turn as a possible stopover, and whenever going THROUGH it is cheaper, update the table. |
| 9 | What does `connected_components` do? | Connected Components: Which nodes can reach which? Components group the network into islands of mutual reachability. |
| 10 | What does `strongly_connected_components` do? | Strongly Connected Components: For DIRECTED networks: groups where every node can reach every OTHER node in the group - and get back. |
| 11 | What does `maximal_clique_bron_kerbosch` do? | Maximal Clique (Bron-Kerbosch): Finds cliques - groups where EVERYONE is connected to everyone. |
| 12 | What does `topological_sort` do? | Topological Sort: For dependency networks (task A before task B...), topological sort lines up all nodes so every prerequisite comes first. |
| 13 | What does `articulation_points` do? | Articulation Points: Articulation points are the load-bearing nodes: remove one and the network splits into islands. |
| 14 | What does `bridges_in_graph` do? | Bridges in Graph: Bridges are the load-bearing EDGES: cut one and the network splits. |
| 15 | What does `degree_centrality` do? | Degree Centrality: The simplest popularity score: how many connections does each node have? Hubs with many links matter simply because so much can flow through them. |
| 16 | What does `closeness_centrality` do? | Closeness Centrality: Averages the SHORTEST hops from one node to every other node - the 'reach everyone fast' score, taught from a reserved slot in supplycm v1.2.1. |
| 17 | What does `betweenness_centrality` do? | Betweenness Centrality: Betweenness counts how often a node sits ON THE SHORT PATH between others - the gatekeeper score. |
| 18 | What does `eigenvector_centrality` do? | Eigenvector Centrality: Status by association: you're important if YOUR neighbors are important. |
| 19 | What does `page_rank` do? | PageRank: The algorithm behind Google, applied to your network: importance flows along edges, distributed across each node's links, with a small damping factor keeping everything honest. |
| 20 | What does `bipartite_matching` do? | Bipartite Matching: Two groups, one set of allowed pairings: drivers and loads, nurses and shifts, tasks and machines. |
| 21 | What does `max_weight_bipartite_matching` do? | Max-Weight Bipartite Matching: Matching with opinions: every possible pairing has a value, and you want the set of pairings with the HIGHEST TOTAL. |
| 22 | What does `min_weight_bipartite_matching` do? | Min-Weight Bipartite Matching: The cost twin: every pairing has a PRICE (time, distance, effort), and you want the full assignment at MINIMUM total cost. |
| 23 | What does `kruskal_mst` do? | Kruskal's Minimum Spanning Tree: Connect all nodes with the cheapest possible set of links: sort every edge by cost, keep adding the cheapest that doesn't create a loop, stop when everything's connected. |
| 24 | What does `prim_mst` do? | Prim's Minimum Spanning Tree: Kruskal's rival with a different strategy: grow ONE connected cluster from a start node, always adding the cheapest edge that reaches a new node. |
| 25 | What does `ford_fulkerson_max_flow` do? | Ford-Fulkerson Max Flow: How much can flow from source to sink at once? Ford-Fulkerson keeps finding paths with spare capacity ('augmenting paths') and pushes flow along them until no path remains. |
| 26 | What does `edmonds_karp_max_flow` do? | Edmonds-Karp Max Flow: Ford-Fulkerson with discipline: always augment along the FEWEST-hops remaining path (BFS choice). |
| 27 | What does `min_cut_max_flow_theorem` do? | Min-Cut / Max-Flow Theorem: The theorem behind max flow: the maximum flow exactly equals the capacity of the cheapest 'cut' - the smallest set of lanes whose removal disconnects source from sink. |
| 28 | What does `min_cut_stoer_wagner` do? | Stoer-Wagner Global Min Cut: Instead of separating one source from one sink, find the CHEAPEST way to split the entire network into two parts - anywhere. |
| 29 | What does `min_cost_flow_cycle_canceling` do? | Min-Cost Flow (Cycle Canceling): Max flow told you HOW MUCH can move; min-cost flow asks the next question: at what CHEAPEST total cost? This version starts with a feasible flow and cancels costly loops - rerouting any cycle whose cancellation saves money - until no improvement remains. |
| 30 | What does `successive_shortest_path` do? | Successive Shortest Path (Min-Cost Flow): The elegant min-cost builder: repeatedly send flow along the CHEAPEST available path (respecting reduced costs), one unit-batch at a time, until demand is met. |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
