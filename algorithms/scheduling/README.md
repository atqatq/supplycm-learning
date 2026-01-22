---
title: "Scheduling Algorithms | supplycm Algorithm Library"
description: "All 40 scheduling algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, scheduling, scheduling, supply chain algorithms"
---

# Scheduling (40 algorithms)

Decide the order of jobs so everything finishes on time.

**Levels:** 9 beginner · 14 intermediate · 17 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [FCFS (First Come, First Served)](fcfs_rule.md) | Beginner | Serve jobs in arrival order - the queue at the bakery counter |
| 2 | [SPT (Shortest Processing Time)](spt_rule.md) | Beginner | Do the quick jobs first |
| 3 | [WSPT (Weighted SPT)](wspt_rule.md) | Intermediate | SPT with money on the table: order jobs by processing time DIVIDED BY weight (importance/profit) |
| 4 | [EDD (Earliest Due Date)](edd_rule.md) | Beginner | Serve whoever is due soonest |
| 5 | [Critical Ratio (CR)](critical_ratio.md) | Intermediate | A blend of urgency and workload: CR = time remaining until due date divided by work remaining |
| 6 | [Least Slack (LS)](least_slack.md) | Intermediate | Slack = time remaining minus work remaining |
| 7 | [Moore-Hodgson Algorithm](moore_hodgson.md) | Advanced | You can't make everyone happy - so minimize how MANY jobs are late |
| 8 | [Tardiness Calculation](tardiness_calculation.md) | Beginner | How late was each job, in total? Tardiness counts only the OVERDUE part: a job finishing 3 days late adds 3; early or on-time adds 0 |
| 9 | [Total Completion Time](total_completion_time.md) | Beginner | The sum of all finishing times - the aggregate time jobs spend in the system |
| 10 | [Total Weighted Tardiness](total_weighted_tardiness.md) | Advanced | Tardiness with stakes: each job's lateness multiplied by its weight (penalty, revenue, importance) |
| 11 | [Johnson's Rule (2-Machine Flow)](johnsons_rule.md) | Intermediate | Two machines in sequence, many jobs: Johnson's Rule sequences them optimally |
| 12 | [Flow Shop Schedule](flow_shop_schedule.md) | Intermediate | All jobs pass through the same machine sequence (cut, then weld, then paint) |
| 13 | [NEH Heuristic](neh_heuristic.md) | Advanced | The strongest practical heuristic for multi-machine flow shops: sort jobs by total workload (biggest first), then insert each into the position that minimizes makespan given jobs already placed |
| 14 | [Makespan (Cmax) Calculation](cmax_calculation.md) | Beginner | When does the last job finally finish? Cmax - the makespan - is the schedule's total length and the promise you make to the customer |
| 15 | [Job Shop Scheduling](job_shop_schedule.md) | Advanced | The general case: each job has its OWN route through machines, in its own order |
| 16 | [Open Shop Scheduling](open_shop_schedule.md) | Advanced | Jobs need all machines, but in ANY order - the route is free |
| 17 | [Two-Machine Open Shop](two_machine_open_shop.md) | Advanced | The tamed case of open shop: two machines, any operation order, and a clean optimal construction - find each machine's biggest job, keep it first on its home machine, sequence the rest around it |
| 18 | [Gantt Chart Data](gantt_chart_data.md) | Beginner | Turns a schedule of (machine, start, end) triples into per-machine rows ready for a Gantt chart - the horizontal bars every scheduler's wall demands |
| 19 | [Earliest Start Schedule](earliest_start_schedule.md) | Intermediate | Project scheduling's workhorse: each task starts the moment its predecessors finish |
| 20 | [Critical Path Method (CPM)](critical_path_method.md) | Intermediate | In every project there's a chain of tasks with ZERO slack - delay any of them and the whole project slips |
| 21 | [Slack Time Calculation](slack_time_calculation.md) | Intermediate | Slack is each task's free delay allowance: how late it can start without moving the project's finish |
| 22 | [PERT Expected Duration](pert_expected_duration.md) | Intermediate | Single-point estimates lie |
| 23 | [RPW Priority (Ranked Positional Weight)](rpw_priority.md) | Advanced | For line balancing and complex networks: a task's priority = its own time PLUS the total time of everything that must follow it |
| 24 | [Line Balancing](line_balancing.md) | Advanced | Assembly lines are a relay of stations; balance means dividing tasks so every station needs about the same time - the slowest station sets the pace for everyone |
| 25 | [LPT (Longest Processing Time)](lpt_rule.md) | Beginner | Assigning jobs to several machines? Start the BIG jobs first |
| 26 | [List Scheduling](list_scheduling.md) | Intermediate | The general-purpose parallel dispatcher: keep a list of jobs, assign each next job to whichever machine frees up first |
| 27 | [SRPT (Shortest Remaining Processing Time)](srpt_rule.md) | Intermediate | SPT that re-evaluates constantly: whenever a new job arrives or a shorter remaining time appears, the machine switches to whoever has the LEAST work left |
| 28 | [Preemptive SPT (Flow Time)](preemptive_spt.md) | Advanced | Computes total flow time when interruptions are allowed: jobs can be paused and resumed as shorter work arrives |
| 29 | [Round-Robin Scheduling](round_robin_scheduling.md) | Intermediate | Every job gets a fixed time slice in turn - everyone shares, nobody hogs |
| 30 | [Parallel Machine Makespan](parallel_machine_cmax.md) | Intermediate | You've assigned jobs to machines - now what's the actual finish time? This computes each machine's load and returns the makespan: the slowest machine's total |
| 31 | [Parallel Station Scheduling](parallel_station_scheduling.md) | Advanced | Like parallel machines, but arrivals matter: jobs SHOW UP over time and stations serve first-come with any free station |
| 32 | [Multifit Algorithm](multifit_algorithm.md) | Advanced | A clever twist on parallel scheduling: binary-search the SMALLEST machine capacity that fits all jobs (like bin packing), then declare that capacity the makespan candidate |
| 33 | [Batch Scheduling](batch_scheduling.md) | Advanced | Group compatible jobs to share setups: items from the same family run together and the changeover is paid once |
| 34 | [Setup-Time-Aware Scheduling](setup_time_aware_scheduling.md) | Advanced | Real machines pay a changeover between DIFFERENT jobs - and the cost depends on the pair (red to blue: quick; red to black: an hour) |
| 35 | [No-Wait Scheduling](no_wait_scheduling.md) | Advanced | Some processes can't wait mid-route: steel must stay hot, chemicals must keep flowing |
| 36 | [Deteriorating Jobs Scheduling](deteriorating_jobs_scheduling.md) | Advanced | Some jobs get HARDER the longer they wait: fresh food spoils, paperwork compounds, machines cool down |
| 37 | [Learning Curve Scheduling](learning_curve_scheduling.md) | Advanced | Repetition makes workers faster: the 100th unit takes less than the 10th |
| 38 | [Resource-Constrained Scheduling](resource_constrained_scheduling.md) | Advanced | Project scheduling's reality check: tasks need PEOPLE and machines, and there aren't enough |
| 39 | [LRPT (Longest Remaining Processing Time)](lrpt_rule.md) | Intermediate | Parallel-machine priority by remaining workload: the job with the MOST work left goes next |
| 40 | [Machine Utilization](machine_utilization.md) | Beginner | The simplest health metric in operations: busy time divided by available time, per machine |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_scheduling.md](../../flashcards/flashcards_scheduling.md)
- Recall drill: [drills/drill_scheduling.md](../../drills/drill_scheduling.md)
