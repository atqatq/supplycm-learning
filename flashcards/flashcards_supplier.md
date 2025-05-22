---
title: "Flashcards: Supplier & Procurement | supplycm Learning"
description: "Spaced-repetition flashcards for all 30 supplycm supplier & procurement algorithms."
keywords: "flashcards, supplier, supply chain, recall"
---

# Flashcards: Supplier & Procurement

30 cards. Cover the answer column, say your answer out loud, then check.
Shuffle the deck once you know the order. Revisit after 1 day, 3 days, 1 week, 1 month.

| # | Prompt | Answer |
|---|--------|--------|
| 1 | What does `weighted_point_method` do? | Weighted Point Method: The simplest honest way to pick a supplier: score each one on each criterion, multiply by how much each criterion matters, and add up. |
| 2 | What does `supplier_evaluation_matrix` do? | Supplier Evaluation Matrix: Turns a table of raw scores into a clean nested structure: supplier -> criterion -> score. |
| 3 | What does `vendor_scorecard` do? | Vendor Scorecard: The weighted scorecard with ranking built in: suppliers, metrics, scores, weights - out come weighted totals and ranks. |
| 4 | What does `on_time_delivery_rate` do? | On-Time Delivery Rate: The workhorse supplier metric: of all deliveries, what share arrived on time? Feed it pairs of (promised date, actual date) and get one percentage. |
| 5 | What does `lead_time_quoted_vs_actual` do? | Lead Time: Quoted vs Actual: Compares what suppliers promise with what they deliver: feed pairs of (quoted, actual) lead times and get the average quoted, the average actual, and the gap. |
| 6 | What does `purchase_order_compliance` do? | Purchase Order Compliance: Measures how well suppliers follow what was actually ordered: right quantities, right items, right timing. |
| 7 | What does `price_analysis` do? | Price Analysis: Feed in a list of quotes or historical prices and get the key statistics in one call: average, spread, cheapest, priciest. |
| 8 | What does `purchase_price_variance` do? | Purchase Price Variance: PPV multiplies the price gap (actual minus standard) by quantity bought: the money version of 'we paid more than planned'. |
| 9 | What does `spend_analysis` do? | Spend Analysis: Rolls up every transaction into spend by category and by supplier, then shows concentration: how much goes to each supplier within each category. |
| 10 | What does `maverick_spend_detection` do? | Maverick Spend Detection: Maverick spend is buying outside agreed contracts and preferred suppliers - quick, well-meaning, and expensive. |
| 11 | What does `supplier_consolidation` do? | Supplier Consolidation: Shows what happens if you move a chosen share of spend to fewer suppliers: the consolidated amount and the remaining spread. |
| 12 | What does `supplier_diversity_index` do? | Supplier Diversity Index: Scores how evenly spend is spread across suppliers on a 0-1 scale: 1 means perfectly spread, near 0 means almost everything goes to one supplier. |
| 13 | What does `negotiation_zone` do? | Negotiation Zone (ZOPA): Given each side's walk-away price, this finds the zone of possible agreement and whether it exists at all. |
| 14 | What does `competitive_bidding` do? | Competitive Bidding: Scores sealed bids by blending price and quality with chosen weights, then names the winner. |
| 15 | What does `contract_compliance_score` do? | Contract Compliance Score: Checks the box list inside a contract - insurance certificates, SLA reports, audits, training - and scores the share actually in place. |
| 16 | What does `supplier_audit_score` do? | Supplier Audit Score: Turns audit findings into section scores: for each area (quality, safety, environment...) you record findings against a maximum, and out come percentage scores per section. |
| 17 | What does `supplier_rating` do? | Composite Supplier Rating: One number to summarize a supplier: scores per dimension (quality, delivery, price...) combined with weights into a single rating. |
| 18 | What does `supplier_risk_score` do? | Supplier Risk Score: Blends risk factors - financial health, country risk, single-source dependency, quality history - with weights into one 0-100 score. |
| 19 | What does `preferred_supplier_index` do? | Preferred Supplier Index: Combines weighted supplier scores against a pass threshold: everyone above the line becomes 'preferred' and gets the easy buying path. |
| 20 | What does `supplier_segmentation` do? | Supplier Segmentation (Kraljic): The Kraljic matrix places every supplier on two axes - profit impact and supply risk - into four boxes: Strategic (high/high), Leverage (high/low), Bottleneck (low/high), Routine (low/low). |
| 21 | What does `total_cost_of_ownership` do? | Total Cost of Ownership (TCO): TCO adds up a purchase's whole life: price plus acquisition (freight, install), operating costs, downtime cost, and disposal. |
| 22 | What does `should_cost_analysis` do? | Should-Cost Analysis: Before negotiating, build the price from scratch: materials, labor hours x rate, overhead, and a fair profit margin. |
| 23 | What does `ahp_supplier_selection` do? | AHP Supplier Selection: AHP takes your pairwise comparisons - 'quality is 3x more important than price' - and turns them into clean criterion weights that always sum to 1. |
| 24 | What does `analytic_network_process` do? | ANP (Analytic Network Process): ANP is AHP's big sibling for messy reality: criteria can influence EACH OTHER, not just the alternatives. |
| 25 | What does `topsis` do? | TOPSIS: TOPSIS ranks alternatives by geometric intuition: the best option is simultaneously closest to an ideal one and farthest from the worst imaginable one. |
| 26 | What does `fuzzy_topsis` do? | Fuzzy TOPSIS: Fuzzy TOPSIS lets judges answer in ranges - 'quality is about 7 to 9, probably 8' - instead of pretending one decimal is truth. |
| 27 | What does `promethee` do? | PROMETHEE: PROMETHEE compares every alternative pair on every criterion, asking 'how MUCH does A beat B here?' via preference thresholds, then sums the evidence into positive and negative flows. |
| 28 | What does `electre` do? | ELECTRE: ELECTRE builds 'outranking' statements: alternative i beats j when enough weighted criteria agree (concordance) AND no single criterion screams against it (discordance). |
| 29 | What does `data_envelopment_analysis` do? | Data Envelopment Analysis (DEA): DEA benchmarks efficiency relatively: each supplier or plant is scored 0-1 by comparing its outputs (deliveries, quality) to its inputs (cost, labor) against a frontier built by the best performers. |
| 30 | What does `strategic_supplier_scorecard` do? | Strategic Supplier Scorecard: The strategic version of a scorecard adds forward-looking KPIs - innovation, improvement, risk management - next to delivery and cost. |

Want more depth? Re-run the "Check yourself" questions on each lesson page.
