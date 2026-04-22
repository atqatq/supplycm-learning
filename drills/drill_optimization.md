---
title: "Recall Drill: Optimization | supplycm Learning"
description: "Active-recall drill with answer key covering all 30 supplycm optimization algorithms."
keywords: "drill, recall, optimization, supply chain practice"
---

# Recall Drill: Optimization

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Binary Search** (`binary_search`)

1. What must be true before binary search works?
2. A million sorted items take how many checks?
3. Where does binary search show up beyond lookup?

**Heap Sort** (`heap_sort`)

4. What does the 'heap' guarantee?
5. Why choose heap sort over quicksort?
6. Where do heaps secretly run your day?

**Merge Sort** (`merge_sort`)

7. Why is merging two SORTED lists cheap?
8. What does 'stable' mean and why care?
9. When would you pick merge over quicksort?

**Quick Sort** (`quick_sort`)

10. What's quicksort's dirty secret?
11. How do real libraries tame the worst case?
12. Quicksort vs merge sort - one-line trade-off?

**Fractional Knapsack** (`fractional_knapsack`)

13. Why is greedy optimal HERE but not for the 0-1 knapsack?
14. What's 'value density'?
15. Where does this model appear in supply chains?

**0-1 Knapsack (Dynamic Programming)** (`knapsack_01_dp`)

16. Why does greedy fail on 0-1 knapsack?
17. What does the DP table remember?
18. What grows painfully here?

**Subset Sum** (`subset_sum`)

19. Why is subset sum hard when summing is trivial?
20. How does DP tame it for moderate numbers?
21. Where does exact-fill matter in supply chains?

**Edit Distance** (`edit_distance`)

22. Why is edit distance better than exact matching for addresses?
23. What does a distance of 1 vs 4 suggest operationally?
24. How does DP build the answer?

**Longest Increasing Subsequence** (`longest_increasing_subsequence`)

25. Why 'subsequence' rather than 'substring'?
26. What would this reveal on weekly demand?
27. Why is brute force painful here?

**Longest Common Subsequence** (`dynamic_programming_lcs`)

28. LCS vs edit distance - how do they relate?
29. Why allow gaps in the match?
30. Where would you use this in supply chains?

**Matrix Chain Multiplication** (`matrix_chain_multiplication`)

31. Why does grouping matter at all?
32. How does DP structure the search?
33. What's the supply chain analogy?

**Convex Hull** (`convex_hull`)

34. What does an interior point mean for delivery territory?
35. Why do hulls help network design?
36. What's the 'turn' test that builds the hull?

**Graph Coloring (Greedy)** (`graph_coloring_greedy`)

37. What do 'colors' represent in scheduling?
38. Why can greedy use more colors than necessary?
39. What's the theoretical floor on colors?

**N-Queens Backtracking** (`n_queens_backtracking`)

40. What is 'backtracking' in one sentence?
41. Why is undoing better than restarting?
42. Where does this pattern appear in real tools?

**Ant Colony Optimization (ACO)** (`ant_colony_optimization`)

43. What do pheromones encode?
44. Why does evaporation matter?
45. ACO vs simulated annealing - different how?

**Genetic Algorithm (GA)** (`genetic_algorithm`)

46. What role does mutation play?
47. Why 'no gradient needed' matters?
48. What's the classic tuning failure?

**Particle Swarm Optimization (PSO)** (`particle_swarm_optimization`)

49. What are the three forces on each particle?
50. PSO vs GA - contrast in one line?
51. When does the swarm underperform?

**Simulated Annealing (SA)** (`simulated_annealing`)

52. Why accept worse moves at all?
53. What does the cooling schedule control?
54. SA vs tabu search - the philosophical difference?

**Tabu Search** (`tabu_search`)

55. What does the tabu list actually store?
56. How does the search escape local optima?
57. Why a SHORT memory?

**Branch and Bound** (`branch_and_bound`)

58. What makes a bound 'good enough to prune'?
59. Why is this better than brute enumeration?
60. What does the 'relaxation' contribute?

**Golden Section Search** (`golden_section_search`)

61. Why 'golden section'?
62. What must the function satisfy?
63. Derivative methods vs this - when choose it?

**Gradient Descent** (`gradient_descent`)

64. What does the learning rate actually control?
65. Where does gradient descent get stuck?
66. Why does it dominate machine learning?

**Newton-Raphson** (`newton_raphson`)

67. Why is Newton's convergence called 'quadratic'?
68. What's Newton's failure mode?
69. Root-finding vs minimizing - the connection?

**Lagrange Multiplier** (`lagrange_multiplier`)

70. What does the multiplier lambda MEAN economically?
71. Why do gradient-based solvers need this machinery?
72. Where do shadow prices show up in business?

**Simplex Method (Linear Programming)** (`simplex_method`)

73. Why walk only the CORNERS?
74. What are 'shadow prices' in the solution?
75. What CAN'T linear programming express?

**P-Median Facility Location** (`p_median`)

76. What does the 'p' fix?
77. Why minimize weighted distance rather than the maximum?
78. How do you choose p wisely?

**Bin Packing: First Fit** (`bin_packing_first_fit`)

79. Why can arrival ORDER waste bins?
80. First fit vs best fit - the precise difference?
81. What's the lower bound no algorithm can beat?

**Bin Packing: Best Fit** (`bin_packing_best_fit`)

82. What does 'best fit' optimize per placement?
83. When does best fit beat first fit, and when not?
84. What's the fundamental limit of all online packing?

**Bin Packing: First Fit Decreasing (FFD)** (`bin_packing_first_fit_decreasing`)

85. Why does sorting biggest-first help so much?
86. What's FFD's guarantee?
87. When is FFD still beaten?

**Set Cover (Greedy)** (`set_cover_greedy`)

88. What does the greedy rule weigh at each step?
89. How far from optimal can greedy be?
90. Where does set cover hide in supply chains?

Total: 90 questions.

## Part 2 - Answer key

1. The data must be sorted - order is what lets each comparison discard half.
2. About 20 - each check halves the range; that's logarithmic speed, the whole magic.
3. Capacity search: 'what's the smallest capacity that fits?' - bisect on the answer, exactly like multifit does.
4. The largest element is always instantly accessible at the top - finding it costs nothing, removing costs little.
5. Its worst case is solid: quicksort can degrade badly on adversarial input; heap sort never does.
6. Operating system schedulers, event queues, Dijkstra's algorithm - anywhere 'next most urgent, please' is asked constantly.
7. One pass with top-of-each comparisons - no element is ever revisited; that's the entire efficiency story.
8. Equal items keep their original relative order - crucial when sorting by one column after another.
9. When worst-case guarantees, stability, or external memory matter - otherwise quicksort's speed usually wins.
10. Its worst case - sorted or adversarial pivots can collapse it toward slow, quadratic behavior.
11. Random pivots, median-of-three, or hybrid fallbacks (introsort switches to heap sort when recursion misbehaves).
12. Speed vs guarantees: quicksort wins on average; merge sort wins on certainty and stability.
13. Fractions erase the awkwardness - leftover space can always be filled with a partial item, so density ordering never misleads.
14. Value divided by weight - the worth of each kilo; loading by density is the whole algorithm.
15. Budget allocation across divisible investments, cargo mixing, and media buying - anywhere partial takes are legal.
16. Density ignores leftover SPACE - the best-density item can strand capacity the second-best would have filled perfectly.
17. The best achievable value for every (items so far, capacity) combination - no scenario is ever recomputed or forgotten.
18. Capacity range and item count - the table's size is their product; huge capacities need different machinery.
19. The number of SUBSETS grows explosively - 2^n candidates; the question is whether an exact needle hides in that haystack.
20. It records which totals are reachable so far - reachability spreads forward, skipping impossible branches entirely.
21. Cutting stock, truck cube-out, batch formulation - 'can these orders combine into one full load?' is subset sum in work clothes.
22. Typos happen - 'Main St' vs 'Main Street' vs 'Maine St' need graded similarity, not binary mismatch.
23. 1: likely the same record with a typo; 4: possibly different entities - thresholds turn distance into decisions.
24. A grid where each cell is the cheapest edit path to that prefix pair - one small comparison per cell, no brute force.
25. Elements need not sit adjacent - the chain can skip noise, which is exactly what makes it robust to dips.
26. The strongest sustained growth thread - weeks that kept outdoing earlier weeks, ignoring the noise between.
27. Every subset and order combination is a candidate - DP instead asks 'best chain ENDING at each item' and chains forward.
28. Two lenses on similarity: LCS counts agreement; edit distance counts corrections needed - one long LCS means small distance.
29. Real sequences drift - plans take different detours but keep the same backbone; gaps forgive the drift while honoring order.
30. Comparing two planners' route sequences or standard vs actual process steps - the shared core shows what both agree happened.
31. Intermediate result SIZES differ - multiplying by a huge intermediate repeatedly is expensive; good grouping keeps intermediates small.
32. Best cost for every (start, end) chain segment, built bottom-up - every split point gets its fair trial.
33. Consolidation order: which shipments merge first determines intermediate handling sizes - the same combinatorial spine.
34. It's covered by the boundary - no special planning needed; the hull defines where service must reach.
35. They bound the geography - perimeter, diameter, and hull area estimate travel effort before any routing.
36. Walking the boundary, every turn must lean the same way - any reverse turn means a point hides inside and gets ejected.
37. Time slots, rooms, or resources - any dimension where conflicting items must separate.
38. Order matters - an unlucky sequence forces early colors a better order would avoid; the clique of conflicts sets the true floor.
39. The largest fully-connected group (clique) needs that many colors - count the triangle, and three is unavoidable.
40. Depth-first search with undo: commit to a choice, explore, and if the branch fails, revert cleanly and try the next.
41. All earlier good choices are preserved - you only unwind the failed decision, not the whole plan.
42. CP solvers, timetabling engines, robot path planners - anywhere 'constraints plus try-and-retreat' describes reality.
43. Collective memory: trails that led to short tours get reinforced, making them more tempting to future ants.
44. It forgets stale wisdom - without evaporation, early bad trails haunt the colony forever.
45. Colony memory vs single-walker temperature: ACO learns a DISTRIBUTION over routes; SA explores alone with cooling luck.
46. Fresh genes: without it, the population inbreeds and stalls on early luck - mutation keeps exploration alive.
47. Many real objectives are bumpy, discrete, or simulation-based - evolution only asks 'better or worse', never 'which slope'.
48. Selection pressure too strong - the population converges prematurely on a mediocre peak; diversity is fuel, spend it wisely.
49. Inertia (keep going), personal best (where I found food), social best (where the swarm found food) - the weights tune the culture.
50. PSO nudges continuous positions socially; GA recombines discrete structures genetically - flocking vs breeding.
51. Wildly multimodal spaces with weak communication - the flock camps on the first decent basin and misses better valleys.
52. Escapology: strict improvement gets trapped at the first local optimum; temporary worse moves are the ticket over the ridge.
53. The patience curve - how long the search stays adventurous before committing; too fast freezes into poor basins.
54. SA explores downhill via temperature luck; tabu remembers and forbids - randomness vs memory as the escape mechanism.
55. Recent moves (or attributes) - short-term memory forbidding their immediate reversal; the loop-breaker.
56. It accepts worsening moves when the improving ones are forbidden - wandering is the price of novelty.
57. Long tabus over-constrain; short ones may loop - the list length is the exploration-exploitation dial in disguise.
58. If the branch's best CASE can't beat the incumbent solution, its actual case can't either - skip it with mathematical peace of mind.
59. Pruned branches cost nothing - the proof of optimality survives while most of the work vanishes.
60. It computes the branch's optimistic ceiling quickly (e.g., allowing fractional decisions) - tight ceilings prune hard; loose ones prune slowly.
61. Probe spacing uses the golden ratio so each iteration reuses one interior point - one new evaluation per step, not two.
62. Unimodality on the range - one valley only; multiple dips can strand the search in the wrong one.
63. When derivatives are unavailable, noisy, or fiddly - golden section asks only 'which probe is lower?'
64. Step size - large strides overshoot and oscillate; small ones converge reliably but slowly; it's the patience dial.
65. Local minima and saddle points on non-convex landscapes - it is honest but nearsighted.
66. Objectives are smooth and gradients are computable - and the rule scales to billions of parameters without cleverness.
67. Roughly, the error squares each step - 0.1 becomes 0.01 becomes 0.0001; accuracy explodes near the root.
68. Bad derivatives or terrible starting points can cycle or diverge - the tangent can point somewhere absurd.
69. Minimizing f means finding where its DERIVATIVE is zero - apply Newton to the derivative and you get optimization (Newton's method in optimization).
70. Shadow price: the objective's improvement per unit of extra constraint - capacity value, budget value, made numeric.
71. Constraints block naive downhill walking - the multiplier folds the fence into the landscape so gradients stay honest.
72. CPLEX-style reports: 'one more hour of machine time is worth X' - every planner should read lambda before buying capacity.
73. Linear objectives peak at vertices - checking every corner in an improving order guarantees the global optimum without interior wandering.
74. The worth of one extra unit of each constraint's resource - the dual values that convert a plan into an investment argument.
75. Fixed costs, minimums, and all-or-nothing logic - those bend lines into curves and require integer or nonlinear extensions.
76. The facility COUNT - the model optimizes WHERE given you've decided HOW MANY; p itself is a business decision.
77. P-median serves the AVERAGE customer well; covering the worst case is the p-CENTER's different philosophy.
78. Solve for p and p+1 and price the improvement - the curve of 'total distance vs facilities' makes the budget conversation honest.
79. A big early item fragments space - first-fit can't save room for the big one still in the queue.
80. First: the earliest bin with room; best: the TIGHTEST fit - best fit leaves big fragments open for future big items.
81. Total size divided by capacity, rounded up - every packing needs at least that many bins.
82. Leftover space minimized - big gaps stay available for big arrivals instead of absorbing small items greedily.
83. Instance-dependent - both are heuristics; the decreasing variant below usually beats both.
84. No lookahead - arrivals are committed as they come; the real gain comes from sorting, i.e., seeing the future.
85. Reversibility: small items fit almost anywhere, big ones almost nowhere - place the inflexible first, improvise with the rest.
86. At most 11/9 of optimal bins (plus a little) - a heuristic with a proof, which is rare and lovely.
87. Awkward item mixes where optimal requires NOT placing greedily - exact methods win small instances; FFD wins everything else in practice.
88. New coverage per pick - the option disclosing the most unseen elements wins, regardless of its total size.
89. Within a log factor - theoretically loose, empirically close; the worst cases are constructed, not typical.
90. DC placement covering all regions, spare-part kits covering failure modes - every 'fewest resources, full coverage' question.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
