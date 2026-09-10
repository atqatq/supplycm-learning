---
title: "Recall Drill: Networks | supplycm Learning"
description: "Active-recall drill with answer key covering all 30 supplycm networks algorithms."
keywords: "drill, recall, network, supply chain practice"
---

# Recall Drill: Networks

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**BFS Shortest Path** (`bfs_shortest_path`)

1. When is BFS the right shortest-path tool?
2. What does BFS guarantee that DFS doesn't?
3. Why 'breadth' first?

**DFS Traversal** (`dfs_traversal`)

4. DFS vs BFS in one line each?
5. What is DFS bad at?
6. Why do so many algorithms build on DFS?

**Bidirectional Search** (`bidirectional_search`)

7. Why is bidirectional search dramatically faster?
8. What does it need to work?
9. When does the trick fail?

**Dijkstra's Shortest Path** (`dijkstra_shortest_path`)

10. What's Dijkstra's golden assumption?
11. Why does it always expand the cheapest frontier node?
12. How does this map to logistics?

**A* Search** (`a_star_search`)

13. What makes a heuristic 'admissible'?
14. Heuristic of constant zero - what does A* become?
15. Why is A* the routing standard?

**Bellman-Ford** (`bellman_ford`)

16. What can Bellman-Ford do that Dijkstra can't?
17. What does a negative cycle mean in business terms?
18. Why is it slower?

**All-Pairs Shortest Path** (`all_pairs_shortest_path`)

19. When would you precompute all pairs instead of on-demand queries?
20. What do infinite entries mean?
21. Directed vs undirected - how does it show here?

**Floyd-Warshall** (`floyd_warshall`)

22. What is the algorithm's one idea?
23. When is Floyd-Warshall preferable to repeated Dijkstra?
24. How would you detect negative cycles with it?

**Connected Components** (`connected_components`)

25. What does it mean if everything is one component?
26. A key supplier's node forms its own island after an edge fails - now what?
27. How is this different from strongly connected components?

**Strongly Connected Components** (`strongly_connected_components`)

28. Why does direction split weakly-connected groups?
29. What's an SCC of size 1 telling you?
30. Where do SCCs matter in supply chains?

**Maximal Clique (Bron-Kerbosch)** (`maximal_clique_bron_kerbosch`)

31. What makes a group a 'clique'?
32. Why 'maximal' and not 'maximum'?
33. What supply chain question is a clique question?

**Topological Sort** (`topological_sort`)

34. What makes an order 'valid'?
35. What happens with a dependency cycle?
36. Why does BOM planning care?

**Articulation Points** (`articulation_points`)

37. What does an articulation point mean operationally?
38. How do you fix a critical articulation point?
39. Do hubs always matter this way?

**Bridges in Graph** (`bridges_in_graph`)

40. Node-critical vs edge-critical - how do they differ?
41. A busy edge that's NOT a bridge - why is that reassuring?
42. How do you eliminate all bridges?

**Degree Centrality** (`degree_centrality`)

43. What does degree centrality MISS?
44. In supply networks, what does high degree suggest?
45. Why normalize by node count?

**Betweenness Centrality** (`betweenness_centrality`)

46. High degree vs high betweenness - when do they disagree?
47. What happens to a network when a top-betweenness node fails?
48. How would you reduce dangerous betweenness?

**Eigenvector Centrality** (`eigenvector_centrality`)

49. How does this differ from degree centrality?
50. Why do scores depend on each other?
51. In supply terms, who is eigenvector-central?

**PageRank** (`page_rank`)

52. What does the damping factor represent?
53. PageRank vs eigenvector centrality - family resemblance?
54. Why does splitting attention matter?

**Bipartite Matching** (`bipartite_matching`)

55. What makes a matching valid?
56. Why can greedy pairing fail?
57. What does an unmatched left node mean operationally?

**Max-Weight Bipartite Matching** (`max_weight_bipartite_matching`)

58. Matching count vs matching value - what's the difference?
59. What does the weight represent in dispatch?
60. Why can't greedy 'best pair first' solve it?

**Min-Weight Bipartite Matching** (`min_weight_bipartite_matching`)

61. When do I use min-weight vs max-weight?
62. What if a pairing is impossible?
63. How does this relate to the Hungarian algorithm?

**Kruskal's Minimum Spanning Tree** (`kruskal_mst`)

64. Why does refusing loops guarantee optimality?
65. What does the MST minimize - and what not?
66. Why is a tree risky for operations?

**Prim's Minimum Spanning Tree** (`prim_mst`)

67. Prim vs Kruskal - when does each feel natural?
68. Does the start node change the total cost?
69. When would the two algorithms choose DIFFERENT edge sets?

**Ford-Fulkerson Max Flow** (`ford_fulkerson_max_flow`)

70. What is an 'augmenting path'?
71. What limits max flow?
72. How is this a supply chain question?

**Edmonds-Karp Max Flow** (`edmonds_karp_max_flow`)

73. What did Edmonds-Karp actually add?
74. Why does BFS-based choice help?
75. Max flow answers capacity - what question comes next?

**Min-Cut / Max-Flow Theorem** (`min_cut_max_flow_theorem`)

76. What does 'min cut = max flow' actually mean?
77. How is the cut useful beyond the number?
78. After widening the bottleneck, what happens?

**Stoer-Wagner Global Min Cut** (`min_cut_stoer_wagner`)

79. Global min cut vs s-t min cut - difference?
80. What does the global weak seam mean for a supply network?
81. How do you harden a weak seam?

**Min-Cost Flow (Cycle Canceling)** (`min_cost_flow_cycle_canceling`)

82. What is a 'negative cost cycle'?
83. How does this differ from max flow?
84. Where does this appear in logistics?

**Successive Shortest Path (Min-Cost Flow)** (`successive_shortest_path`)

85. Why does 'cheapest path first' yield a global optimum?
86. Cycle canceling vs successive shortest path - style difference?
87. What practical inputs must be honest here?

**Closeness Centrality** (`closeness_centrality` - reserved slot in v1.2.1)

88. What does closeness centrality count that degree centrality misses?
89. In supply chain words, what does a high-closeness warehouse give you?
90. Both ends of a line network have 1 link each - why does closeness still favor the middle node?

Total: 90 questions.

## Part 2 - Answer key

1. When all links cost the same - then fewest hops equals cheapest path.
2. Shortest (fewest-edge) paths in unweighted graphs - DFS wanders and may find long paths first.
3. It expands the whole frontier level by level, like ripples - hence breadth, not depth.
4. DFS dives deep then backtracks; BFS sweeps level by level - deep vs wide.
5. Shortest paths in unweighted graphs - it happily reports long routes discovered first.
6. Its backtrack structure naturally exposes cycles, bridges, and components - the graph's skeleton.
7. Each side explores a ring whose size grows exponentially - two half-depth rings are far smaller than one full-depth ring.
8. A clear target to search backward from, and edges you can legally traverse in reverse.
9. Directed networks where reverse edges are invalid, or when the target is vague rather than specific.
10. No negative costs - the 'cheapest so far' logic breaks if a later edge could subtract cost.
11. Greedy certainty: once popped, no cheaper route can ever appear - that's the proof's whole trick.
12. Nodes are locations, edges are lanes with cost per shipment - Dijkstra answers 'cheapest way from A to everywhere'.
13. It never overestimates the true remaining cost - optimism keeps A* from skipping the true best path.
14. Plain Dijkstra - the hunch is gone, so full exploration returns.
15. Road networks come with natural estimates (straight-line distance), and the savings are enormous.
16. Survive negative edge costs AND report negative cycles - Dijkstra returns nonsense on both.
17. A profitable loop - ship around it forever and gain endlessly; arbitrage, or a data error worth fixing.
18. It relaxes ALL edges repeatedly without Dijkstra's greedy shortcut - the price of paranoia.
19. When many downstream models (routing, location) will query constantly - compute once, reuse everywhere.
20. Unreachable pairs - no directed path exists; a red flag in supply networks worth investigating.
21. One-way lanes produce asymmetric tables - cheap going, impossible returning; real road networks hide these surprises.
22. For each possible stopover k, test whether i-to-k-to-j beats i-to-j - repeat for all k and optimality falls out.
23. Dense graphs and small-to-medium n - its simplicity wins; for sparse graphs, repeated Dijkstra usually wins.
24. A diagonal entry turning negative - the node found a profitable loop through itself.
25. Full cohesion - every node reaches every other; no structural isolation.
26. You've found a broken link to repair - or an exposure that needs a backup lane.
27. Weak components ignore direction (any path); strong components demand round-trips - much stricter.
28. Because reaching OUT is not reaching BACK - one-way links fail the mutual test.
29. That node cannot return to itself - a dead-end or pure source in the flow structure.
30. Return loops: reverse logistics and closed-loop cycles need genuine mutual reachability to function.
31. Complete interconnection - every member connects to every other; remove one link and it stops being maximal.
32. Maximal: can't add anyone more; maximum: the largest possible size. Bron-Kerbosch lists ALL maximal ones, from which the maximum is read off.
33. 'Which SKUs can run on the SAME line configuration with zero changeover between any pair?' - full mutual compatibility.
34. Every edge points from earlier to later - no task precedes its own prerequisite.
35. No valid order exists - the sort comes up short; the cycle is a design bug to unwind.
36. Exploding a BOM requires parents before children in planning logic - topological order guarantees it.
37. A node whose failure disconnects others - the network's single points of failure, by definition.
38. Add a bypass edge or node around it - redundancy converts critical into survivable.
39. No - a hub with redundant connections can fail without splitting anything; criticality is about STRUCTURE, not traffic volume.
40. Articulation points fail as NODES; bridges fail as LINKS - networks often have different ones of each.
41. Traffic would reroute - the network survives its loss; busy is not the same as critical.
42. Add parallel or alternative edges until every link sits on a cycle - redundancy by construction.
43. Position: a node with 2 well-placed links can matter more than one with 5 in a corner - degree ignores location.
44. Consolidation - many flows share this node; efficient, but also concentrated risk.
45. So networks of different sizes compare fairly - a 3-link node in a tiny net isn't automatically a hub.
46. Bridge nodes: few links, all of them essential - low degree, high betweenness.
47. Paths lengthen or break between whole regions - connectivity degrades disproportionately.
48. Add a bypass lane or second gatekeeper - split the gatekeeping, share the risk.
49. Quality over quantity - connections to important nodes count more than connections to periphery.
50. That's the definition: my score is built from my neighbors' scores - the math solves them all simultaneously.
51. Suppliers of suppliers - you may not trade with them directly, but their health propagates through your network.
52. The chance a random surfer jumps anywhere - it stabilizes the math and stops dead-ends from swallowing all the score.
53. Close cousins - PageRank adds damping and outgoing-link splitting; eigenvector is the purer version.
54. A node with many outgoing links passes less to each - endorsing everyone means standing for nothing.
55. Each node appears at most once - no driver takes two loads, no load rides two trucks.
56. A greedy first pick can steal a partner someone else desperately needs - real matching algorithms 'undo' earlier choices.
57. Unmet demand - either add capacity (more right nodes) or loosen compatibility edges.
58. Weighted versions trade pair COUNT for pair QUALITY - sometimes fewer, better pairs win outright.
59. Profit, priority, or fit score per pairing - the matrix is your business judgment in numbers.
60. Early best-pairs can block later great pairs - the optimal set sometimes sacrifices a good single for a great combo.
61. Costs (minimize) vs benefits (maximize) - flip signs and they're the same algorithm wearing different clothes.
62. Set its cost to a huge number - effectively forbidden, and the math routes around it.
63. It IS the classic assignment problem - Hungarian is the famous solution method for exactly this.
64. Any loop's priciest edge is redundant - Kruskal's never-create-a-loop rule quietly enforces that logic.
65. Total connection cost - NOT distances or failure risk; those need extra edges beyond the tree.
66. No redundancy - cut any edge and the network splits; MSTs are cheap, not resilient.
67. Prim grows from a hub (operations love it); Kruskal sorts all edges globally (planners love it) - same optimum, different story.
68. No - the MST cost is unique even when edge choices tie; start wherever you like.
69. On ties - multiple optimal trees can exist; both are equally cheap.
70. Any source-to-sink route with unused capacity remaining - each one found adds flow until none survive.
71. The narrowest cut of the network - total flow equals the smallest set of lanes whose removal disconnects source from sink.
72. It's literally 'how much can we ship per period through this network?' - capacity planning in one number.
73. A rule: always the shortest augmenting path - turning 'it works' into 'it works in bounded time'.
74. Short paths saturate quickly and don't zigzag - the number of augmentations stays provably small.
75. Minimum cost of achieving that flow - which is exactly the min-cost-flow family's business.
76. Perfection: no flow can beat the narrowest cut, and some flow achieves exactly it - the ceiling and the best attempt coincide.
77. It NAMES the binding lanes - investment goes there, not to politically loud but non-binding lanes.
78. A different cut becomes minimum - bottlenecks migrate; capacity planning is a chain of these discoveries.
79. No chosen endpoints - the weakest split ANYWHERE; s-t versions only look at lines between two named nodes.
80. The natural fracture line under stress - where regional disruption would split the network first.
81. Add capacity across it or duplicate the flow role on both sides - make the crack expensive to propagate.
82. A loop you could reroute flow around and SAVE money - canceling them is the whole optimization.
83. Max flow maximizes quantity; min-cost flow achieves a REQUIRED quantity at minimum cost - different questions, related machinery.
84. Multi-lane freight assignment with capacities - the workhorse behind network flow planning modules.
85. Reduced costs keep every future choice honest - each batch extends the optimal solution rather than spoiling it.
86. Fix-then-fix vs build-right-the-first-time - same optimum, opposite workflows.
87. Capacities, lane costs, and supplies - the model optimizes exactly what you encode; sloppy costs give confidently wrong plans.
88. Shortest hops to EVERYONE - it averages how far a node sits from all others, while degree only counts direct links.
89. Fewer hops to every store, plant, and customer - faster service and quicker rebalancing from one well-placed spot.
90. Placement beats size: the middle sits 1-2 hops from everyone, while the two ends are far from each other - link counts can't see that.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
