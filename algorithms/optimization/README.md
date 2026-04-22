---
title: "Optimization Algorithms | supplycm Algorithm Library"
description: "All 30 optimization algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, optimization, optimization, supply chain algorithms"
---

# Optimization (30 algorithms)

Classic tools for squeezing the best out of limited resources.

**Levels:** 2 beginner · 14 intermediate · 14 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [Binary Search](binary_search.md) | Beginner | Find an item in a SORTED list by halving: check the middle, discard half, repeat |
| 2 | [Heap Sort](heap_sort.md) | Intermediate | Sort by tournament: arrange items in a 'heap' where the biggest always sits on top, repeatedly pluck the winner, and rebuild |
| 3 | [Merge Sort](merge_sort.md) | Intermediate | Divide and conquer refined: split the list in half, sort each half, then ZIP the sorted halves together with a merge pass |
| 4 | [Quick Sort](quick_sort.md) | Intermediate | Pick a pivot, split items into smaller and larger, sort the two sides, repeat |
| 5 | [Fractional Knapsack](fractional_knapsack.md) | Beginner | Fill a limited capacity with the best value: take items by value density (value per kilo), best first, and allow FRACTIONS of the last item that doesn't quite fit |
| 6 | [0-1 Knapsack (Dynamic Programming)](knapsack_01_dp.md) | Intermediate | The indivisible version: each item is taken fully or not at all, and greedy density famously fails |
| 7 | [Subset Sum](subset_sum.md) | Intermediate | Is there a subset of these numbers that adds up EXACTLY to the target? Deceptively simple, famously hard in general - and solvable by dynamic programming when numbers are reasonable |
| 8 | [Edit Distance](edit_distance.md) | Intermediate | How many single-letter edits (insert, delete, replace) turn one word into another? 'kitten' to 'sitting' takes 3 |
| 9 | [Longest Increasing Subsequence](longest_increasing_subsequence.md) | Advanced | The longest run (not necessarily adjacent) of values that keep rising through a sequence |
| 10 | [Longest Common Subsequence](dynamic_programming_lcs.md) | Advanced | The longest pattern two sequences SHARE in order (gaps allowed): 'ABCBDAB' and 'BDCABA' share 'BDAB' |
| 11 | [Matrix Chain Multiplication](matrix_chain_multiplication.md) | Advanced | Multiplying a chain of matrices, the GROUPING changes the cost wildly: (AB)C can be cheap where A(BC) is expensive |
| 12 | [Convex Hull](convex_hull.md) | Intermediate | Stretch a rubber band around all your points: the band's shape is the convex hull - the tightest boundary containing everything |
| 13 | [Graph Coloring (Greedy)](graph_coloring_greedy.md) | Intermediate | Assign 'colors' so no two connected nodes share one: exam timetables (no student sits two exams at once), shift assignments, channel allocation |
| 14 | [N-Queens Backtracking](n_queens_backtracking.md) | Advanced | Place N chess queens where none attacks another |
| 15 | [Ant Colony Optimization (ACO)](ant_colony_optimization.md) | Advanced | Digital ants lay pheromone on routes they walk; better (shorter) routes get walked more, reinforced more, and eventually the colony converges on strong paths |
| 16 | [Genetic Algorithm (GA)](genetic_algorithm.md) | Advanced | Evolution as an algorithm: a population of candidate solutions breeds - the fittest become parents, children mix their traits (crossover) and mutate - and generations roll forward toward better answers |
| 17 | [Particle Swarm Optimization (PSO)](particle_swarm_optimization.md) | Advanced | A flock of candidate solutions flies through the search space: each particle remembers its personal best AND hears about the swarm's best, then blends momentum toward both |
| 18 | [Simulated Annealing (SA)](simulated_annealing.md) | Advanced | Accept better moves always; occasionally accept WORSE ones early (high temperature) so the search can escape traps, then cool down and grow conservative |
| 19 | [Tabu Search](tabu_search.md) | Advanced | Local search with a memory: keep a short 'tabu list' of recent moves and FORBID reversing them, forcing the search out of loops and through worse terrain to reach new regions |
| 20 | [Branch and Bound](branch_and_bound.md) | Advanced | Exact optimization with pruning: split the problem into branches, and whenever a branch's best HOPED-FOR value can't beat what you've already found, abandon it without exploring |
| 21 | [Golden Section Search](golden_section_search.md) | Intermediate | Finding the lowest point of a curve WITHOUT derivatives: probe two interior points of a range, keep the side holding the minimum, shrink, repeat |
| 22 | [Gradient Descent](gradient_descent.md) | Intermediate | Walk downhill: measure the slope (gradient) at your position, step the opposite way, repeat |
| 23 | [Newton-Raphson](newton_raphson.md) | Advanced | Finding where a function crosses zero, using curvature: jump to where the tangent line hits zero, repeat |
| 24 | [Lagrange Multiplier](lagrange_multiplier.md) | Advanced | Optimize a goal while respecting a constraint - by pricing the constraint |
| 25 | [Simplex Method (Linear Programming)](simplex_method.md) | Advanced | The grandfather of optimization: maximize a linear objective under linear constraints by walking along the feasible region's CORNERS, each step improving, until no corner is better |
| 26 | [P-Median Facility Location](p_median.md) | Advanced | Choose exactly p facility locations among candidates to minimize total weighted DISTANCE to demand |
| 27 | [Bin Packing: First Fit](bin_packing_first_fit.md) | Intermediate | Pack items into the fewest capacity-limited bins: place each item into the FIRST bin with room, open a new bin only when nothing fits |
| 28 | [Bin Packing: Best Fit](bin_packing_best_fit.md) | Intermediate | First fit's tidy sibling: place each item into the bin it fits MOST SNUGLY - the smallest remaining space that still holds it - preserving big gaps for future big items |
| 29 | [Bin Packing: First Fit Decreasing (FFD)](bin_packing_first_fit_decreasing.md) | Intermediate | The famously effective upgrade: SORT items biggest-first, then apply first fit |
| 30 | [Set Cover (Greedy)](set_cover_greedy.md) | Intermediate | Cover every requirement with the fewest facilities/warehouses/skills: repeatedly pick the option covering the most UNCOVERED requirements so far |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_optimization.md](../../flashcards/flashcards_optimization.md)
- Recall drill: [drills/drill_optimization.md](../../drills/drill_optimization.md)
