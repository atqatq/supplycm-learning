---
title: "Recall Drill: Supplier & Procurement | supplycm Learning"
description: "Active-recall drill with answer key covering all 30 supplycm supplier & procurement algorithms."
keywords: "drill, recall, supplier, supply chain practice"
---

# Recall Drill: Supplier & Procurement

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Weighted Point Method** (`weighted_point_method`)

1. Why set weights before seeing the scores?
2. Scores are 1-10. Can they be any scale?
3. Two suppliers tie. What now?

**Supplier Evaluation Matrix** (`supplier_evaluation_matrix`)

4. What shape is the output?
5. Before weighting, what should you check in the raw matrix?
6. A supplier has a missing score. What do you do?

**Vendor Scorecard** (`vendor_scorecard`)

7. What do the weights decide here?
8. Why publish the same scorecard every period?
9. A supplier ranks last but is your only source. Now what?

**On-Time Delivery Rate** (`on_time_delivery_rate`)

10. What counts as 'on time' - early too?
11. OTD fell from 95% to 85%. First questions?
12. Why does OTD drive your safety stock?

**Lead Time: Quoted vs Actual** (`lead_time_quoted_vs_actual`)

13. Which is more damaging: a 2-day bias or occasional 10-day spikes?
14. Who should own closing this gap?
15. Where should the 'actual' number end up?

**Purchase Order Compliance** (`purchase_order_compliance`)

16. What does a compliance score actually measure?
17. Why do substitutions and short-ships hurt planning?
18. Compliance is 99% but service is terrible. How?

**Price Analysis** (`price_analysis`)

19. What does a very wide price spread tell you?
20. All quotes move up 8% together. Supplier problem or market problem?
21. Why always ask for the outlier's breakdown?

**Purchase Price Variance** (`purchase_price_variance`)

22. What makes PPV 'unfavorable'?
23. Why can chasing PPV hurt quality?
24. Standard price is 10.0 and hasn't changed in 2 years. Risk?

**Spend Analysis** (`spend_analysis`)

25. What is 'spend concentration' and why care?
26. Name two savings opportunities spend analysis reveals.
27. You see 500 tiny suppliers in office supplies. Action?

**Maverick Spend Detection** (`maverick_spend_detection`)

28. Why does maverick spend happen even with good contracts?
29. Is all non-contract buying bad?
30. What is the healthiest fix?

**Supplier Consolidation** (`supplier_consolidation`)

31. What do you gain by consolidating suppliers?
32. What do you risk?
33. How many suppliers is 'right' for a category?

**Supplier Diversity Index** (`supplier_diversity_index`)

34. Index drops from 0.8 to 0.3 in a year. What happened?
35. Is a high diversity index always good?
36. Two categories, same index. Same risk?

**Negotiation Zone (ZOPA)** (`negotiation_zone`)

37. What is a walk-away price?
38. No zone exists. What are your options?
39. Why should your walk-away stay private?

**Competitive Bidding** (`competitive_bidding`)

40. What happens if you shift to 50/50 weights?
41. When is competitive bidding the wrong tool?
42. How do you stop bidders gaming quality scores?

**Contract Compliance Score** (`contract_compliance_score`)

43. Why reduce a contract to checkboxes?
44. Which terms usually fail first?
45. Score improved 60% to 95% - done?

**Supplier Audit Score** (`supplier_audit_score`)

46. Why score sections separately instead of one total?
47. What is the follow-up ritual after a low section score?
48. Findings doubled at the same supplier year over year. Interpretations?

**Composite Supplier Rating** (`supplier_rating`)

49. Why never report the single rating alone?
50. Quality 0.6 vs 0.4 weight - who wins the argument?
51. Rating slipped from 88 to 84. Next step?

**Supplier Risk Score** (`supplier_risk_score`)

52. Which risk factor is usually weighted heaviest and why?
53. Risk score rises 20 points in one quarter. Response?
54. Why score ALL critical suppliers, not just the scary ones?

**Preferred Supplier Index** (`preferred_supplier_index`)

55. What does the threshold actually control?
56. A long-time supplier drops below threshold. Now what?
57. How does this connect to maverick spend?

**Supplier Segmentation (Kraljic)** (`supplier_segmentation`)

58. Name the four Kraljic quadrants and one tactic each.
59. Where does the office stationery supplier sit?
60. A bottleneck supplier just raised prices 30%. Options?

**Total Cost of Ownership (TCO)** (`total_cost_of_ownership`)

61. Which TCO line do buyers most often forget?
62. How does TCO change supplier conversations?
63. Over what horizon should you compute TCO?

**Should-Cost Analysis** (`should_cost_analysis`)

64. What inputs build a should-cost model?
65. The supplier says 'our overhead is higher'. Response?
66. When is should-cost a waste of time?

**AHP Supplier Selection** (`ahp_supplier_selection`)

67. What does a pairwise entry of 3 mean?
68. Why must AHP weights sum to 1?
69. Judgments contradict each other. What does AHP do about it?

**ANP (Analytic Network Process)** (`analytic_network_process`)

70. When does ANP beat plain AHP?
71. What does inner_dependence encode?
72. Cost of ANP over AHP?

**TOPSIS** (`topsis`)

73. What do 'benefit' and 'cost' criteria mean here?
74. Why must criteria be normalized first?
75. TOPSIS picks A, your gut says B. Next move?

**Fuzzy TOPSIS** (`fuzzy_topsis`)

76. What is a triangular fuzzy number?
77. When is fuzzy scoring worth the extra effort?
78. Fuzzy TOPSIS and classic TOPSIS disagree. Why?

**PROMETHEE** (`promethee`)

79. What does the indifference threshold do?
80. Positive vs negative flow - what does each measure?
81. Two options have near-equal flows. Decision?

**ELECTRE** (`electre`)

82. What role does the discordance threshold play?
83. ELECTRE returns no relation between A and B. Meaning?
84. Concordance 0.7 means what?

**Data Envelopment Analysis (DEA)** (`data_envelopment_analysis`)

85. What does an efficiency score of 0.75 mean?
86. Why is DEA fair for comparing different-sized units?
87. A small unit scores 1.0 and a giant 0.7. Is the small one 'better'?

**Strategic Supplier Scorecard** (`strategic_supplier_scorecard`)

88. What KPIs belong on a STRATEGIC scorecard that a routine one skips?
89. Supplier scores 95 on quality, 60 on innovation. Consequence?
90. Why show weighted contributions per KPI?

Total: 90 questions.

## Part 2 - Answer key

1. To stop tuning weights to crown the supplier you already liked - weights are strategy, not tactics.
2. Yes - points, 0-100, whatever; just keep every criterion on a comparable scale and state it.
3. Revisit weights (maybe they reveal a real tie), or break the tie on the criterion with the biggest risk.
4. A dict of dicts: suppliers as keys, each holding criterion -> score.
5. That all criteria point the same way (higher = better) - flip cost-type scores if needed.
6. Score it before comparison - gaps quietly bias totals and hide real differences.
7. How the trade-offs resolve - raise the delivery weight and Beta can overtake Alpha.
8. Trends beat snapshots - a supplier sliding from 88 to 81 is a conversation starter.
9. Scorecards inform, not decide: build an improvement plan (or a backup) rather than just dropping them.
10. Usually promised-or-before, but very early can also hurt (storage, expiry). Define it in the contract.
11. Which products/lanes slipped, and is it capacity, quality holds, or data errors? Segment before you accuse.
12. Late deliveries behave like demand spikes - you buffer stock against the supplier's unreliability.
13. Both hurt differently - bias shifts every order late; spikes cause rare deep stockouts. Fix bias first, buffer for spikes.
14. Purchasing owns the conversation; planning owns the parameter change if the gap persists.
15. In your ERP lead time fields - plans built on quoted numbers inherit every miss.
16. The share of orders executed as written - quantities, items, and dates matching the PO.
17. Each one silently invalidates an assumption in MRP and schedules - plans rot line by line.
18. You may be ordering the wrong things perfectly - compliance measures execution, not strategy.
19. Quotes may not be like-for-like (specs, terms, volumes) or the market is inefficient - investigate before deciding.
20. Likely market - raw materials or exchange rates. Your negotiation lever changes accordingly.
21. It either hides a real cost difference you can learn from, or padding you can negotiate away.
22. Actual price above standard - you paid more than the plan assumed.
23. Buyers squeeze price, suppliers quietly cheapen the product - total cost rises elsewhere.
24. The standard itself is stale; variances then measure inflation, not buyer skill - refresh the standards.
25. The share of a category going to one supplier - high share means leverage for you, but risk if they fail.
26. Consolidating fragmented suppliers, and spotlighting maverick/off-contract spend.
27. Consolidate to 1-3 with better terms - transaction costs alone justify it.
28. Urgency, ignorance of contracts, or friction in the official process - fix the process, not just the people.
29. Occasionally it finds better deals - investigate outliers instead of blanket-punishing.
30. Make the compliant path the easiest path: catalogs, one-click approvals, and clear guidance.
31. Volume discounts, fewer relationships to manage, deeper collaboration, better service priority.
32. Dependency: a failure, price hike, or quality slip hits harder with fewer alternatives.
33. Enough for competition and security (often 2-3) - decide per category on criticality, not globally.
34. Spend concentrated - a consolidation program, a single-sourcing decision, or a competitor exit. Verify it was deliberate.
35. No - over-fragmentation loses leverage. The index flags concentration risk; strategy decides the sweet spot.
36. Not necessarily - risk also depends on switch costs and market depth, which the index cannot see.
37. The point where walking out beats dealing - your Best Alternative (BATNA) defines it.
38. Change the deal itself: volumes, payment terms, specs, timing - expand the pie until zones overlap, or accept no deal.
39. Once revealed, the other side only ever offers just above it.
40. Quality matters more - here Beta's case strengthens; publish weights BEFORE bids to keep the process fair.
41. Strategic partnerships and complex specs - there, negotiation and total-cost analysis beat one-round bidding.
42. Score quality on evidence (audits, samples, track record), not self-declared claims.
43. Because unverified clauses are wishes; a score forces someone to evidence each one.
44. The boring ones: current insurance certificates, tested contingency plans, up-to-date compliance reports.
45. No - compliance drifts; set a review cadence or it slides back within two quarters.
46. Improvement needs a target - 'environment 50%' directs effort, 'overall 78%' does not.
47. Corrective actions with owners and dates, then a re-check - the next audit verifies closure, not intentions.
48. Worse performance OR better detection - compare against process changes before concluding either.
49. An 85 can hide a failing dimension - always show component scores so problems stay visible.
50. Whoever can justify the weight with business impact - weights are policy, not math.
51. Open the dimensions, find the mover, and ask the supplier for a corrective plan - before the trend settles.
52. Often financial or concentration - a bankrupt or irreplaceable supplier can stop your line entirely.
53. Investigate the driver immediately - score jumps usually mean something real changed.
54. Because risk migrates quietly - the boring supplier of last year may be the crisis of this one.
55. How exclusive the preferred list is - too low and it means nothing, too high and buyers route around it.
56. Same rule as everyone: remediation plan with a date, or lose preferred status - consistency builds program trust.
57. It shrinks it: when preferred suppliers are genuinely good and easy to buy from, going around them stops making sense.
58. Strategic: partnership; Leverage: compete the business; Bottleneck: secure supply/stock up; Routine: automate and simplify.
59. Routine - low impact, low risk; the goal is minimal effort via catalogs and p-cards.
60. Qualify alternatives, redesign the spec, hold buffer stock - the quadrant's whole point is to never be surprised here.
61. Downtime - an hour of stopped production can erase a year of unit-price savings.
62. It moves them from 'your price is 3% high' to 'your downtime cost is 40k' - specific, quantified, actionable.
63. The realistic ownership life - long enough to include operating and end-of-life, short enough that estimates stay honest.
64. Material quantities and prices, labor hours and rates, overhead allocation, and a fair margin.
65. Ask to see the drivers - volume, utilization, process. Should-cost is a conversation starter, not an ultimatum.
66. On small spends or true commodities with transparent markets - the model costs more than the savings.
67. The row criterion is 3 times more important than the column criterion (and the mirror cell is 1/3).
68. So they are shares of importance - comparable and complete, with no hidden extra weight.
69. The averaging exposes inconsistency - big contradictions show up as odd weights and get reconsidered.
70. When criteria influence one another - e.g., supplier reputation affects perceived quality - and ignoring it would skew weights.
71. How criteria inside a cluster shape each other, as its own mini comparison matrix.
72. Many more judgments to collect - use it when the decision is big enough to deserve the rigor.
73. Benefit: more is better (quality). Cost: less is better (price) - TOPSIS flips cost columns before comparing.
74. Raw units differ (points vs dollars); normalization puts everything on one fair scale before weighting.
75. Inspect the inputs - usually a weight or a criterion direction disagrees with reality; the method only reflects what you fed it.
76. A best-estimate range (low, most-likely, high) - honesty about imprecision, written as three numbers.
77. When inputs are judgments from people - the ranges carry real information that single numbers destroy.
78. Different treatment of uncertainty - if the fuzzy winner sits inside your ranges' noise, the difference may not be meaningful.
79. Differences smaller than it count as a tie - it stops decimals deciding outcomes that are practically equal.
80. Positive: how strongly this option beats others; negative: how strongly it loses. Net flow combines them.
81. Treat as a tie - break with strategy (risk, relationship, capacity), not by inventing precision.
82. It is the veto: one criterion being bad enough can block an outranking no matter how well the rest score.
83. Incomparability - the evidence does not crown either; decide with other information.
84. At least 70% of criterion weight must support 'i at least as good as j' before i can outrank it.
85. This unit could produce its current outputs with about 75% of the inputs the best performers would need.
86. It compares ratios and builds each unit's own reference frontier - scale matters less than conversion efficiency.
87. At converting inputs to outputs, yes - but check absolute capacity and strategic fit before crowning anyone.
88. Innovation, continuous improvement, risk transparency, and joint-planning participation.
89. A development conversation with concrete expectations - strategic suppliers must bring ideas, not just parts.
90. So both sides see exactly which line moved the total - reviews become about specific gaps, not vibes.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
