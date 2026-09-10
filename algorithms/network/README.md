---
title: "Networks Algorithms | supplycm Algorithm Library"
description: "All 30 networks algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, network, networks, supply chain algorithms"
---

# Networks (30 algorithms)

Find paths, hubs, and weak points in a network of places.

**Levels:** 4 beginner · 9 intermediate · 17 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [BFS Shortest Path](bfs_shortest_path.md) | Beginner | Breadth-first search explores a network in rings: all direct neighbors, then neighbors-of-neighbors |
| 2 | [DFS Traversal](dfs_traversal.md) | Beginner | Depth-first search dives deep: follow one path as far as it goes, backtrack, try the next |
| 3 | [Bidirectional Search](bidirectional_search.md) | Intermediate | Search from BOTH ends at once: BFS forward from the start and backward from the target, until the waves meet in the middle |
| 4 | [Dijkstra's Shortest Path](dijkstra_shortest_path.md) | Intermediate | The workhorse of weighted routing: from the start, always expand the CHEAPEST known node next, updating neighbors' best distances |
| 5 | [A* Search](a_star_search.md) | Intermediate | Dijkstra with a hunch: A* adds a heuristic - an estimate of remaining distance to the goal - and explores in the direction of promise |
| 6 | [Bellman-Ford](bellman_ford.md) | Advanced | The careful shortest-path algorithm: relax every edge repeatedly, and even NEGATIVE costs are handled correctly |
| 7 | [All-Pairs Shortest Path](all_pairs_shortest_path.md) | Advanced | Instead of one origin, run shortest paths between EVERY pair of nodes in one structured pass |
| 8 | [Floyd-Warshall](floyd_warshall.md) | Advanced | The elegant all-pairs algorithm: consider each node in turn as a possible stopover, and whenever going THROUGH it is cheaper, update the table |
| 9 | [Connected Components](connected_components.md) | Beginner | Which nodes can reach which? Components group the network into islands of mutual reachability |
| 10 | [Strongly Connected Components](strongly_connected_components.md) | Advanced | For DIRECTED networks: groups where every node can reach every OTHER node in the group - and get back |
| 11 | [Maximal Clique (Bron-Kerbosch)](maximal_clique_bron_kerbosch.md) | Advanced | Finds cliques - groups where EVERYONE is connected to everyone |
| 12 | [Topological Sort](topological_sort.md) | Intermediate | For dependency networks (task A before task B...), topological sort lines up all nodes so every prerequisite comes first |
| 13 | [Articulation Points](articulation_points.md) | Advanced | Articulation points are the load-bearing nodes: remove one and the network splits into islands |
| 14 | [Bridges in Graph](bridges_in_graph.md) | Advanced | Bridges are the load-bearing EDGES: cut one and the network splits |
| 15 | [Degree Centrality](degree_centrality.md) | Beginner | The simplest popularity score: how many connections does each node have? Hubs with many links matter simply because so much can flow through them |
| 16 | [Closeness Centrality](closeness_centrality.md) | Intermediate | How fast can this node reach EVERYONE? Average the shortest hops to all others - low average distance, high closeness |
| 17 | [Betweenness Centrality](betweenness_centrality.md) | Intermediate | Betweenness counts how often a node sits ON THE SHORT PATH between others - the gatekeeper score |
| 18 | [Eigenvector Centrality](eigenvector_centrality.md) | Advanced | Status by association: you're important if YOUR neighbors are important |
| 19 | [PageRank](page_rank.md) | Advanced | The algorithm behind Google, applied to your network: importance flows along edges, distributed across each node's links, with a small damping factor keeping everything honest |
| 20 | [Bipartite Matching](bipartite_matching.md) | Intermediate | Two groups, one set of allowed pairings: drivers and loads, nurses and shifts, tasks and machines |
| 21 | [Max-Weight Bipartite Matching](max_weight_bipartite_matching.md) | Advanced | Matching with opinions: every possible pairing has a value, and you want the set of pairings with the HIGHEST TOTAL |
| 22 | [Min-Weight Bipartite Matching](min_weight_bipartite_matching.md) | Advanced | The cost twin: every pairing has a PRICE (time, distance, effort), and you want the full assignment at MINIMUM total cost |
| 23 | [Kruskal's Minimum Spanning Tree](kruskal_mst.md) | Intermediate | Connect all nodes with the cheapest possible set of links: sort every edge by cost, keep adding the cheapest that doesn't create a loop, stop when everything's connected |
| 24 | [Prim's Minimum Spanning Tree](prim_mst.md) | Intermediate | Kruskal's rival with a different strategy: grow ONE connected cluster from a start node, always adding the cheapest edge that reaches a new node |
| 25 | [Ford-Fulkerson Max Flow](ford_fulkerson_max_flow.md) | Advanced | How much can flow from source to sink at once? Ford-Fulkerson keeps finding paths with spare capacity ('augmenting paths') and pushes flow along them until no path remains |
| 26 | [Edmonds-Karp Max Flow](edmonds_karp_max_flow.md) | Advanced | Ford-Fulkerson with discipline: always augment along the FEWEST-hops remaining path (BFS choice) |
| 27 | [Min-Cut / Max-Flow Theorem](min_cut_max_flow_theorem.md) | Advanced | The theorem behind max flow: the maximum flow exactly equals the capacity of the cheapest 'cut' - the smallest set of lanes whose removal disconnects source from sink |
| 28 | [Stoer-Wagner Global Min Cut](min_cut_stoer_wagner.md) | Advanced | Instead of separating one source from one sink, find the CHEAPEST way to split the entire network into two parts - anywhere |
| 29 | [Min-Cost Flow (Cycle Canceling)](min_cost_flow_cycle_canceling.md) | Advanced | Max flow told you HOW MUCH can move; min-cost flow asks the next question: at what CHEAPEST total cost? This version starts with a feasible flow and cancels costly loops - rerouting any cycle whose cancellation saves money - until no improvement remains |
| 30 | [Successive Shortest Path (Min-Cost Flow)](successive_shortest_path.md) | Advanced | The elegant min-cost builder: repeatedly send flow along the CHEAPEST available path (respecting reduced costs), one unit-batch at a time, until demand is met |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_network.md](../../flashcards/flashcards_network.md)
- Recall drill: [drills/drill_network.md](../../drills/drill_network.md)
