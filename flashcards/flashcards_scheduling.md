---
title: "Flashcards: Scheduling | supplycm Learning"
description: "Spaced-repetition flashcards for all 40 supplycm scheduling algorithms."
keywords: "flashcards, scheduling, supply chain, recall"
---

# Flashcards: Scheduling

40 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `fcfs_rule` do? | FCFS (First Come, First Served): Serve jobs in arrival order - the queue at the bakery counter. |
| 2 | What does `spt_rule` do? | SPT (Shortest Processing Time): Do the quick jobs first. |
| 3 | What does `wspt_rule` do? | WSPT (Weighted SPT): SPT with money on the table: order jobs by processing time DIVIDED BY weight (importance/profit). |
| 4 | What does `edd_rule` do? | EDD (Earliest Due Date): Serve whoever is due soonest. |
| 5 | What does `critical_ratio` do? | Critical Ratio (CR): A blend of urgency and workload: CR = time remaining until due date divided by work remaining. |
| 6 | What does `least_slack` do? | Least Slack (LS): Slack = time remaining minus work remaining. |
| 7 | What does `moore_hodgson` do? | Moore-Hodgson Algorithm: You can't make everyone happy - so minimize how MANY jobs are late. |
| 8 | What does `tardiness_calculation` do? | Tardiness Calculation: How late was each job, in total? Tardiness counts only the OVERDUE part: a job finishing 3 days late adds 3; early or on-time adds 0. |
| 9 | What does `total_completion_time` do? | Total Completion Time: The sum of all finishing times - the aggregate time jobs spend in the system. |
| 10 | What does `total_weighted_tardiness` do? | Total Weighted Tardiness: Tardiness with stakes: each job's lateness multiplied by its weight (penalty, revenue, importance). |
| 11 | What does `johnsons_rule` do? | Johnson's Rule (2-Machine Flow): Two machines in sequence, many jobs: Johnson's Rule sequences them optimally. |
| 12 | What does `flow_shop_schedule` do? | Flow Shop Schedule: All jobs pass through the same machine sequence (cut, then weld, then paint). |
| 13 | What does `neh_heuristic` do? | NEH Heuristic: The strongest practical heuristic for multi-machine flow shops: sort jobs by total workload (biggest first), then insert each into the position that minimizes makespan given jobs already placed. |
| 14 | What does `cmax_calculation` do? | Makespan (Cmax) Calculation: When does the last job finally finish? Cmax - the makespan - is the schedule's total length and the promise you make to the customer. |
| 15 | What does `job_shop_schedule` do? | Job Shop Scheduling: The general case: each job has its OWN route through machines, in its own order. |
| 16 | What does `open_shop_schedule` do? | Open Shop Scheduling: Jobs need all machines, but in ANY order - the route is free. |
| 17 | What does `two_machine_open_shop` do? | Two-Machine Open Shop: The tamed case of open shop: two machines, any operation order, and a clean optimal construction - find each machine's biggest job, keep it first on its home machine, sequence the rest around it. |
| 18 | What does `gantt_chart_data` do? | Gantt Chart Data: Turns a schedule of (machine, start, end) triples into per-machine rows ready for a Gantt chart - the horizontal bars every scheduler's wall demands. |
| 19 | What does `earliest_start_schedule` do? | Earliest Start Schedule: Project scheduling's workhorse: each task starts the moment its predecessors finish. |
| 20 | What does `critical_path_method` do? | Critical Path Method (CPM): In every project there's a chain of tasks with ZERO slack - delay any of them and the whole project slips. |
| 21 | What does `slack_time_calculation` do? | Slack Time Calculation: Slack is each task's free delay allowance: how late it can start without moving the project's finish. |
| 22 | What does `pert_expected_duration` do? | PERT Expected Duration: Single-point estimates lie. |
| 23 | What does `rpw_priority` do? | RPW Priority (Ranked Positional Weight): For line balancing and complex networks: a task's priority = its own time PLUS the total time of everything that must follow it. |
| 24 | What does `line_balancing` do? | Line Balancing: Assembly lines are a relay of stations; balance means dividing tasks so every station needs about the same time - the slowest station sets the pace for everyone. |
| 25 | What does `lpt_rule` do? | LPT (Longest Processing Time): Assigning jobs to several machines? Start the BIG jobs first. |
| 26 | What does `list_scheduling` do? | List Scheduling: The general-purpose parallel dispatcher: keep a list of jobs, assign each next job to whichever machine frees up first. |
| 27 | What does `srpt_rule` do? | SRPT (Shortest Remaining Processing Time): SPT that re-evaluates constantly: whenever a new job arrives or a shorter remaining time appears, the machine switches to whoever has the LEAST work left. |
| 28 | What does `preemptive_spt` do? | Preemptive SPT (Flow Time): Computes total flow time when interruptions are allowed: jobs can be paused and resumed as shorter work arrives. |
| 29 | What does `round_robin_scheduling` do? | Round-Robin Scheduling: Every job gets a fixed time slice in turn - everyone shares, nobody hogs. |
| 30 | What does `parallel_machine_cmax` do? | Parallel Machine Makespan: You've assigned jobs to machines - now what's the actual finish time? This computes each machine's load and returns the makespan: the slowest machine's total. |
| 31 | What does `parallel_station_scheduling` do? | Parallel Station Scheduling: Like parallel machines, but arrivals matter: jobs SHOW UP over time and stations serve first-come with any free station. |
| 32 | What does `multifit_algorithm` do? | Multifit Algorithm: A clever twist on parallel scheduling: binary-search the SMALLEST machine capacity that fits all jobs (like bin packing), then declare that capacity the makespan candidate. |
| 33 | What does `batch_scheduling` do? | Batch Scheduling: Group compatible jobs to share setups: items from the same family run together and the changeover is paid once. |
| 34 | What does `setup_time_aware_scheduling` do? | Setup-Time-Aware Scheduling: Real machines pay a changeover between DIFFERENT jobs - and the cost depends on the pair (red to blue: quick; red to black: an hour). |
| 35 | What does `no_wait_scheduling` do? | No-Wait Scheduling: Some processes can't wait mid-route: steel must stay hot, chemicals must keep flowing. |
| 36 | What does `deteriorating_jobs_scheduling` do? | Deteriorating Jobs Scheduling: Some jobs get HARDER the longer they wait: fresh food spoils, paperwork compounds, machines cool down. |
| 37 | What does `learning_curve_scheduling` do? | Learning Curve Scheduling: Repetition makes workers faster: the 100th unit takes less than the 10th. |
| 38 | What does `resource_constrained_scheduling` do? | Resource-Constrained Scheduling: Project scheduling's reality check: tasks need PEOPLE and machines, and there aren't enough. |
| 39 | What does `lrpt_rule` do? | LRPT (Longest Remaining Processing Time): Parallel-machine priority by remaining workload: the job with the MOST work left goes next. |
| 40 | What does `machine_utilization` do? | Machine Utilization: The simplest health metric in operations: busy time divided by available time, per machine. |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
