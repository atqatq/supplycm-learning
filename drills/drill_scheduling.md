---
title: "Recall Drill: Scheduling | supplycm Learning"
description: "Active-recall drill with answer key covering all 40 supplycm scheduling algorithms."
keywords: "drill, recall, scheduling, supply chain practice"
---

# Recall Drill: Scheduling

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**FCFS (First Come, First Served)** (`fcfs_rule`)

1. What is FCFS's biggest operational weakness?
2. When is FCFS genuinely the right rule?
3. Why keep FCFS as a benchmark?

**SPT (Shortest Processing Time)** (`spt_rule`)

4. What does SPT provably minimize?
5. What's SPT's dark side?
6. How do real shops fix starvation?

**WSPT (Weighted SPT)** (`wspt_rule`)

7. What ratio does WSPT rank by?
8. WSPT is optimal for which measure?
9. All weights equal - what does WSPT become?

**EDD (Earliest Due Date)** (`edd_rule`)

10. What does EDD provably minimize?
11. EDD vs SPT conflict - when does each win the argument?
12. How do you combine both instincts?

**Critical Ratio (CR)** (`critical_ratio`)

13. What does CR below 1 mean?
14. Why is CR better than pure EDD in busy shops?
15. How often should CR be recomputed?

**Least Slack (LS)** (`least_slack`)

16. How does slack differ from critical ratio?
17. When do LS and EDD agree?
18. What's LS's blind spot?

**Moore-Hodgson Algorithm** (`moore_hodgson`)

19. What exactly does Moore-Hodgson minimize?
20. Who gets evicted when a conflict appears?
21. After the algorithm, what's your negotiation list?

**Tardiness Calculation** (`tardiness_calculation`)

22. What counts as zero tardiness?
23. Why is total tardiness hard to optimize?
24. What's the difference between tardiness and lateness?

**Total Completion Time** (`total_completion_time`)

25. Which rule provably minimizes total completion time?
26. Why does finishing short jobs early help everyone?
27. What does this metric ignore that tardiness catches?

**Total Weighted Tardiness** (`total_weighted_tardiness`)

28. How do weights change the scheduling conversation?
29. Why no simple optimal rule here?
30. What sequence does intuition suggest?

**Johnson's Rule (2-Machine Flow)** (`johnsons_rule`)

31. What's the rule for the smallest time found?
32. What does Johnson minimize exactly?
33. Why does machine 2 matter most?

**Flow Shop Schedule** (`flow_shop_schedule`)

34. What is a flow shop, formally?
35. What is makespan?
36. Why do more machines make this hard?

**NEH Heuristic** (`neh_heuristic`)

37. What are NEH's two phases?
38. Why does 'biggest first' work as insertion order?
39. NEH vs Johnson's Rule - when each?

**Makespan (Cmax) Calculation** (`cmax_calculation`)

40. Makespan vs average completion - what's the difference?
41. Why do sales teams care about makespan?
42. Can two orders share the same makespan?

**Job Shop Scheduling** (`job_shop_schedule`)

43. Flow shop vs job shop - the essential difference?
44. What makes job shop scheduling famously hard?
45. What's the practical approach for real shops?

**Open Shop Scheduling** (`open_shop_schedule`)

46. What freedom does an open shop give that flow shop doesn't?
47. Why is 2-machine open shop special?
48. What does 'no idle time on both machines simultaneously' imply?

**Two-Machine Open Shop** (`two_machine_open_shop`)

49. What is the makespan lower bound here?
50. Why does the biggest single job anchor the schedule?
51. What breaks the elegance at 3+ machines?

**Gantt Chart Data** (`gantt_chart_data`)

52. What does a gap between bars on one machine mean?
53. Why visualize before executing schedules?
54. What belongs on the horizontal axis?

**Earliest Start Schedule** (`earliest_start_schedule`)

55. What does 'earliest start' assume away?
56. Why is this the fastest possible?
57. How does this feed critical path analysis?

**Critical Path Method (CPM)** (`critical_path_method`)

58. What makes a task 'critical'?
59. Can there be multiple critical paths?
60. A non-critical task slips 2 days. Project impact?

**Slack Time Calculation** (`slack_time_calculation`)

61. What does negative slack mean?
62. How do you use slack of 5 days constructively?
63. Where does all the project's delay risk live?

**PERT Expected Duration** (`pert_expected_duration`)

64. What's the standard PERT blend?
65. Why does the expected value skew low?
66. What does the variance tell you?

**RPW Priority (Ranked Positional Weight)** (`rpw_priority`)

67. What does 'positional weight' capture?
68. When does RPW shine over simple time rules?
69. How does RPW relate to critical path?

**Line Balancing** (`line_balancing`)

70. What does cycle time mean on a line?
71. Why does one slow station rule the line?
72. What's the theoretical minimum number of stations?

**LPT (Longest Processing Time)** (`lpt_rule`)

73. Why do big jobs go first on parallel machines?
74. How good is LPT's guarantee?
75. What would beat LPT here?

**List Scheduling** (`list_scheduling`)

76. What makes list scheduling so widely used?
77. Does the list order matter?
78. When does list scheduling struggle?

**SRPT (Shortest Remaining Processing Time)** (`srpt_rule`)

79. How does SRPT differ from plain SPT?
80. What's SRPT's cost?
81. Why is it optimal for average flow time?

**Preemptive SPT (Flow Time)** (`preemptive_spt`)

82. What does 'preemption' permit?
83. When is preemption unrealistic?
84. Why does preemption help average waits?

**Round-Robin Scheduling** (`round_robin_scheduling`)

85. What does the quantum control?
86. Why do completion times converge under round-robin?
87. When is round-robin the wrong choice?

**Parallel Machine Makespan** (`parallel_machine_cmax`)

88. What sets the makespan on parallel machines?
89. Why is perfect balance often impossible?
90. What's the lower bound any schedule must respect?

**Parallel Station Scheduling** (`parallel_station_scheduling`)

91. What drives waiting here?
92. How do you decide the number of stations?
93. When do more stations NOT help?

**Multifit Algorithm** (`multifit_algorithm`)

94. What is being binary-searched?
95. Why connect scheduling to bin packing?
96. What's multifit's guarantee?

**Batch Scheduling** (`batch_scheduling`)

97. What's the trade-off batching buys and pays?
98. When do large batches backfire?
99. How does this connect to SMED lean thinking?

**Setup-Time-Aware Scheduling** (`setup_time_aware_scheduling`)

100. Why does job ORDER change total setup cost?
101. What problem does this secretly resemble?
102. How does SMED interact with this?

**No-Wait Scheduling** (`no_wait_scheduling`)

103. What's the core tension in no-wait systems?
104. Why does job order matter MORE here?
105. What process would explode under no-wait?

**Deteriorating Jobs Scheduling** (`deteriorating_jobs_scheduling`)

106. How do deteriorating times change scheduling math?
107. Does SPT still work here?
108. What real systems quietly face deterioration?

**Learning Curve Scheduling** (`learning_curve_scheduling`)

109. What does a learning rate of 0.9 mean?
110. How should scheduling exploit learning?
111. When does the curve reset?

**Resource-Constrained Scheduling** (`resource_constrained_scheduling`)

112. What does adding resources do to the CPM result?
113. Where's the first place to look when schedules slip?
114. What's the classic remedy toolbox?

**LRPT (Longest Remaining Processing Time)** (`lrpt_rule`)

115. How does LRPT differ from LPT?
116. What's LRPT protecting against?
117. When does SPT-style thinking beat LRPT?

**Machine Utilization** (`machine_utilization`)

118. Why is 100% utilization a warning, not a trophy?
119. How do utilization numbers guide staffing?
120. Utilization vs efficiency - difference?

Total: 120 questions.

## Part 2 - Answer key

1. Long jobs block short ones - average waiting time balloons when a monster job arrives early.
2. When arrival order IS the promise (service counters) or when switching costs punish cleverness.
3. It quantifies what smarter rules buy you - the gap is the value of scheduling itself.
4. Average (mean) completion time on a single machine - it is optimal for that measure.
5. Starvation: big jobs keep getting pushed back - forever, if small ones keep arriving.
6. Aging rules: jobs get priority as they wait, blending SPT's speed with fairness.
7. Processing time over weight - equivalently, weight per unit of machine time; highest density first.
8. Total weighted completion time - literally the best possible order for that objective.
9. Plain SPT - the special case where every job matters equally.
10. Maximum lateness - the single worst lateness any job suffers.
11. EDD when penalties explode for the latest job; SPT when average service time rules.
12. Composite rules (like critical ratio) blend due-date urgency with processing need - EDD and SPT are its two extremes.
13. The job cannot make its due date even if started now - it needs expediting or a reset promise.
14. It weighs due dates against the WORK required - a far deadline with huge workload deserves urgency too.
15. Continuously or at each dispatch - both clock and remaining work move as the day runs.
16. Slack subtracts (time - work); CR divides - slack is absolute, CR is relative; they reorder differently.
17. When jobs' workloads are similar - then slack ordering collapses to due-date ordering.
18. It ignores job VALUE - a 5-minute-urgent trivial job outranks a massive revenue job with slightly more slack.
19. The NUMBER of tardy jobs - not how late they are, just how many miss.
20. The longest processing job among those considered - clearing the most future time per complaint.
21. The evicted jobs - now you renegotiate their dates with evidence that keeping them would break MORE promises.
22. Any job finishing at or before its due date - earliness is free, lateness is priced.
23. It's stubbornly non-linear - small order changes can swing totals wildly; that's why heuristics and rules exist.
24. Lateness can be negative (early); tardiness floors at zero - tardiness is what customers and penalties actually feel.
25. SPT - shortest processing time first, no tie-breaking required.
26. Each unfinished job blocks ALL followers - short jobs early unblock the queue sooner for the collective.
27. Due dates - a sequence can minimize total time and still humiliate the one job with a hard promise.
28. They convert lateness into money - now a 2-day slip on a key account can outweigh 10-day slips on trivia.
29. Weighted tardiness is NP-hard - even clever heuristics only approximate; simulations and local search earn their keep.
30. High-weight, soon-due jobs early - a blend of WSPT and EDD instincts, then let the metric judge.
31. If it belongs to machine 1, schedule that job from the FRONT; machine 2 times fill from the BACK.
32. Makespan for 2-machine flow shops - total completion of everything, optimally.
33. It's the bottleneck risk: keep it continuously busy and nothing waits at the end - that's the whole insight.
34. All jobs share one routing - same machines, same order; only the sequence is free.
35. The moment the LAST job finishes - the schedule's total length and the factory's promise to the customer.
36. Idle patterns compound - with 3+ machines, no simple rule is optimal; the problem turns famously difficult.
37. Sort jobs by total processing (descending), then insert each greedily at its best position.
38. Big jobs constrain the schedule most - placing them early prevents late regret.
39. Johnson: exactly 2 machines, provably optimal. NEH: 3+ machines, no optimality promise but excellent in practice.
40. Makespan watches the LAST finisher; average watches everyone's experience - sequences can win one and lose the other.
41. It IS the delivery promise - the factory's next free moment starts where makespan ends.
42. Easily - many orders tie on makespan while differing wildly on waits; that's why multiple metrics matter.
43. Flow: everyone shares one route. Job shop: routes are personal - that freedom is what makes it brutally hard.
44. Combinatorial explosion plus deadlock risks - optimal solutions exist but finding them scales terribly.
45. Priority dispatching (this function) plus bottleneck focus - perfect optimality is rarely worth the wait.
46. Operation ORDER per job - the scheduler may permute each job's route to dodge conflicts.
47. Longest-processing-time logic solves it neatly - one of scheduling's rare clean results.
48. The famous Graham bound: makespan can be kept near the natural load limit - open shops are tamer than job shops.
49. The larger of the two machines' total loads - you cannot finish faster than the busier machine works.
50. It risks idling its opposite machine - placing it first lets the other machine feed during its reign.
51. Interactions multiply - the clean construction no longer guarantees optimality; heuristics return.
52. Idle time - capacity nobody used; sometimes inevitable, sometimes the improvement target.
53. Eyes catch overlaps, starvation, and absurdities that numbers hide - one glance beats one spreadsheet.
54. Time - bars span start to end per operation; length is duration, position is the promise.
55. Resource limits - infinite workers and machines; reality's constraints come later (that's RCPSP).
56. Every task starts as early as physics (dependencies) allows - no calendar slack exists to remove.
57. The finish times reveal which chains are tight - pairs perfectly with slack calculation.
58. Zero slack: its earliest and latest feasible times coincide - any delay moves the project end.
59. Yes - parallel chains can tie; delaying any one of them delays the project.
60. None - until its slack runs out; then it becomes critical and the path shifts.
61. The task is already late relative to the promised finish - the deadline needs revisiting or the task needs crashing.
62. Move the task (or its people) by up to 5 days to smooth resource peaks - free flexibility, use it deliberately.
63. On zero-slack tasks - that's where buffer and attention belong.
64. (Optimistic + 4 x most likely + pessimistic) / 6 - a weighted bet that reality sits near 'most likely'.
65. The formula weights 'most likely' four-fold - distributions with long pessimistic tails still average below their worst case.
66. Estimate confidence - high-variance tasks deserve buffers and watching, not just planning.
67. The full downstream burden - a task is as heavy as itself plus its entire future chain.
68. Networked tasks - it respects structure that 'longest task first' ignores entirely.
69. It's a cousin: both price downstream consequences, but RPW produces a dispatch order, not a path.
70. The rhythm between consecutive finished units - set by the customer's demand (takt) or by the slowest station.
71. Everything queues behind it - the line's output equals the bottleneck station's output.
72. Total task time divided by cycle time, rounded up - reality needs more when precedence blocks perfect packing.
73. They can't be split - placing them early lets many small jobs fill the residual gaps on the other machines.
74. Within about 4/3 of optimal makespan on identical machines - excellent for a one-line rule.
75. Exact methods for small instances, or multifit-style binary search on the capacity - often for marginal gains.
76. It accepts ANY priority order and never needs lookahead - perfect for dynamic, changing shops.
77. Enormously - the same mechanic with LPT vs SPT can double the makespan; the policy is the schedule.
78. When jobs need specific machines or setups - pure 'next free' logic ignores those realities unless extended.
79. SPT decides once at the start; SRPT re-decides at every completion AND considers partial progress.
80. Context switching and starvation of big jobs - the same SPT trade-off, sharpened by preemption.
81. Finishing anything sooner unblocks the queue sooner - greedily minimizing the next finish dominates, provably.
82. Pausing a running job to start another, resuming later - time is conserved, attention is flexible.
83. When setups dominate - pausing a furnace or a print run costs real re-setup time that the pure model ignores.
84. It lets tiny arrivals jump the queue instantly instead of waiting behind the current giant - the queue never blocks.
85. Slice size: tiny quanta maximize fairness but add switching overhead; large quanta drift toward FCFS behavior.
86. Everyone advances in parallel - nobody finishes early, but nobody waits forever either.
87. When variance matters more than fairness - tight due dates prefer priority rules over equal slices.
88. The heaviest-loaded machine - every other machine's idle time is hidden behind it.
89. Jobs are indivisible - sums rarely tie exactly; the art is minimizing the unavoidable spread.
90. Total work divided by machines, and the biggest single job - makespan can never beat the larger of the two.
91. Arrival bunching: when several arrive before any station frees, queues form - no rule avoids physics.
92. Simulate candidates: adds stations until waiting (and its cost) stops justifying the station cost.
93. When arrivals are sparse - idle stations cost money without removing any wait that exists.
94. Machine capacity: can all jobs pack into k machines of capacity C? Shrink C until packing barely fails.
95. Identical machines + makespan C = pack all jobs into bins of size C - the problems are twins.
96. Within about 1.2 of optimal - stronger than LPT's guarantee, at slightly more computation.
97. Fewer setups (paid) versus waiting for batch groups (cost) - jobs lose independence to gain efficiency.
98. High holding cost or urgent jobs - big batches delay individual items and stack inventory.
99. SMED shrinks setup cost itself - as setups get cheap, optimal batches shrink, and flexibility returns.
100. Setups depend on consecutive PAIRS - sequencing similar jobs together makes most setups cheap or zero.
101. The Traveling Salesman Problem - cities are jobs, distances are setup times; that's why it's hard and heuristics matter.
102. They multiply: cheaper setups (SMED) make sequencing less critical; big setups make sequencing a gold mine.
103. Jobs refuse to wait, so all slack moves to machines - utilization absorbs what flow time refuses to.
104. Each pair of jobs has a fixed start-time offset (like a headway) - sequencing becomes choosing pairwise offsets, TSP-style.
105. Anything with a cure, dry, or hold step - forcing no-wait there either breaks physics or idles the plant.
106. Completion of later jobs depends on ALL earlier delays - scheduling becomes about minimizing compounded growth.
107. Yes, remarkably - shortest base processing first remains optimal in classic models; the theorem survives deterioration.
108. Perishable supply chains, tax filing, maintenance backlogs - all priced by how long work sits.
109. Each doubling of repetition cuts time to 90% - a classic 90% learning curve from manufacturing history.
110. Cluster similar work early - the learned speed then applies to the many jobs that follow.
111. New product, new tooling, staff rotation - every change re-opens the expensive learning window.
112. Dates stretch whenever tasks compete for the same limited pool - critical paths shift dynamically.
113. Resource contention peaks - periods where demand exceeds capacity; level or add there.
114. Split or shuffle flexible tasks (use their slack), add capacity briefly, or re-sequence - in that order of cheapness.
115. LPT sorts ONCE by total time; LRPT re-ranks continuously by REMAINING time as jobs progress - a living priority.
116. Big jobs finishing late because small ones kept jumping the queue - longest-remaining first pins big jobs early.
117. When average WAIT matters more than makespan - shortest-remaining serves the most jobs soonest; LRPT serves the makespan instead.
118. No buffer survives - any breakdown, rush order, or absentee has nowhere to be absorbed.
119. Persistently low machines are candidates for consolidation or reassignment; hot ones get help.
120. Utilization measures BUSY; efficiency measures productive output while busy - a machine can be 100% busy making scrap.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
