---
title: "Supplier & Procurement Algorithms | supplycm Algorithm Library"
description: "All 30 supplier & procurement algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, supplier, supplier & procurement, supply chain algorithms"
---

# Supplier & Procurement (30 algorithms)

Pick suppliers, score them, and keep them honest.

**Levels:** 8 beginner · 15 intermediate · 7 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [Weighted Point Method](weighted_point_method.md) | Beginner | The simplest honest way to pick a supplier: score each one on each criterion, multiply by how much each criterion matters, and add up |
| 2 | [Supplier Evaluation Matrix](supplier_evaluation_matrix.md) | Beginner | Turns a table of raw scores into a clean nested structure: supplier -> criterion -> score |
| 3 | [Vendor Scorecard](vendor_scorecard.md) | Beginner | The weighted scorecard with ranking built in: suppliers, metrics, scores, weights - out come weighted totals and ranks |
| 4 | [On-Time Delivery Rate](on_time_delivery_rate.md) | Beginner | The workhorse supplier metric: of all deliveries, what share arrived on time? Feed it pairs of (promised date, actual date) and get one percentage |
| 5 | [Lead Time: Quoted vs Actual](lead_time_quoted_vs_actual.md) | Intermediate | Compares what suppliers promise with what they deliver: feed pairs of (quoted, actual) lead times and get the average quoted, the average actual, and the gap |
| 6 | [Purchase Order Compliance](purchase_order_compliance.md) | Intermediate | Measures how well suppliers follow what was actually ordered: right quantities, right items, right timing |
| 7 | [Price Analysis](price_analysis.md) | Intermediate | Feed in a list of quotes or historical prices and get the key statistics in one call: average, spread, cheapest, priciest |
| 8 | [Purchase Price Variance](purchase_price_variance.md) | Beginner | PPV multiplies the price gap (actual minus standard) by quantity bought: the money version of 'we paid more than planned' |
| 9 | [Spend Analysis](spend_analysis.md) | Beginner | Rolls up every transaction into spend by category and by supplier, then shows concentration: how much goes to each supplier within each category |
| 10 | [Maverick Spend Detection](maverick_spend_detection.md) | Intermediate | Maverick spend is buying outside agreed contracts and preferred suppliers - quick, well-meaning, and expensive |
| 11 | [Supplier Consolidation](supplier_consolidation.md) | Intermediate | Shows what happens if you move a chosen share of spend to fewer suppliers: the consolidated amount and the remaining spread |
| 12 | [Supplier Diversity Index](supplier_diversity_index.md) | Intermediate | Scores how evenly spend is spread across suppliers on a 0-1 scale: 1 means perfectly spread, near 0 means almost everything goes to one supplier |
| 13 | [Negotiation Zone (ZOPA)](negotiation_zone.md) | Intermediate | Given each side's walk-away price, this finds the zone of possible agreement and whether it exists at all |
| 14 | [Competitive Bidding](competitive_bidding.md) | Intermediate | Scores sealed bids by blending price and quality with chosen weights, then names the winner |
| 15 | [Contract Compliance Score](contract_compliance_score.md) | Intermediate | Checks the box list inside a contract - insurance certificates, SLA reports, audits, training - and scores the share actually in place |
| 16 | [Supplier Audit Score](supplier_audit_score.md) | Intermediate | Turns audit findings into section scores: for each area (quality, safety, environment...) you record findings against a maximum, and out come percentage scores per section |
| 17 | [Composite Supplier Rating](supplier_rating.md) | Beginner | One number to summarize a supplier: scores per dimension (quality, delivery, price...) combined with weights into a single rating |
| 18 | [Supplier Risk Score](supplier_risk_score.md) | Intermediate | Blends risk factors - financial health, country risk, single-source dependency, quality history - with weights into one 0-100 score |
| 19 | [Preferred Supplier Index](preferred_supplier_index.md) | Intermediate | Combines weighted supplier scores against a pass threshold: everyone above the line becomes 'preferred' and gets the easy buying path |
| 20 | [Supplier Segmentation (Kraljic)](supplier_segmentation.md) | Beginner | The Kraljic matrix places every supplier on two axes - profit impact and supply risk - into four boxes: Strategic (high/high), Leverage (high/low), Bottleneck (low/high), Routine (low/low) |
| 21 | [Total Cost of Ownership (TCO)](total_cost_of_ownership.md) | Intermediate | TCO adds up a purchase's whole life: price plus acquisition (freight, install), operating costs, downtime cost, and disposal |
| 22 | [Should-Cost Analysis](should_cost_analysis.md) | Intermediate | Before negotiating, build the price from scratch: materials, labor hours x rate, overhead, and a fair profit margin |
| 23 | [AHP Supplier Selection](ahp_supplier_selection.md) | Advanced | AHP takes your pairwise comparisons - 'quality is 3x more important than price' - and turns them into clean criterion weights that always sum to 1 |
| 24 | [ANP (Analytic Network Process)](analytic_network_process.md) | Advanced | ANP is AHP's big sibling for messy reality: criteria can influence EACH OTHER, not just the alternatives |
| 25 | [TOPSIS](topsis.md) | Advanced | TOPSIS ranks alternatives by geometric intuition: the best option is simultaneously closest to an ideal one and farthest from the worst imaginable one |
| 26 | [Fuzzy TOPSIS](fuzzy_topsis.md) | Advanced | Fuzzy TOPSIS lets judges answer in ranges - 'quality is about 7 to 9, probably 8' - instead of pretending one decimal is truth |
| 27 | [PROMETHEE](promethee.md) | Advanced | PROMETHEE compares every alternative pair on every criterion, asking 'how MUCH does A beat B here?' via preference thresholds, then sums the evidence into positive and negative flows |
| 28 | [ELECTRE](electre.md) | Advanced | ELECTRE builds 'outranking' statements: alternative i beats j when enough weighted criteria agree (concordance) AND no single criterion screams against it (discordance) |
| 29 | [Data Envelopment Analysis (DEA)](data_envelopment_analysis.md) | Advanced | DEA benchmarks efficiency relatively: each supplier or plant is scored 0-1 by comparing its outputs (deliveries, quality) to its inputs (cost, labor) against a frontier built by the best performers |
| 30 | [Strategic Supplier Scorecard](strategic_supplier_scorecard.md) | Intermediate | The strategic version of a scorecard adds forward-looking KPIs - innovation, improvement, risk management - next to delivery and cost |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_supplier.md](../../flashcards/flashcards_supplier.md)
- Recall drill: [drills/drill_supplier.md](../../drills/drill_supplier.md)
