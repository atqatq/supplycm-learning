---
title: "Quality Algorithms | supplycm Algorithm Library"
description: "All 7 quality algorithms from supplycm explained in plain English with runnable Python examples."
keywords: "supplycm, quality, quality, supply chain algorithms"
---

# Quality (7 algorithms)

Count defects the Six Sigma way and keep processes in control.

**Levels:** 2 beginner · 5 intermediate · 0 advanced. Every page follows the same rhythm: plain English, a runnable example, a "check yourself" recall test, and a small challenge. No math beyond +, -, ×, ÷.

Read top to bottom the first time - the order goes from easiest to hardest.

| # | Algorithm | Level | One-line idea |
|---|-----------|-------|---------------|
| 1 | [DPMO (Defects Per Million Opportunities)](dpmo.md) | Beginner | DPMO scales your defect count to 'how many mistakes would we make per million chances?' |
| 2 | [Sigma Level](sigma_level.md) | Beginner | Sigma level converts DPMO into the famous Six Sigma scale |
| 3 | [Process Capability (Cp)](process_capability_cp.md) | Intermediate | Cp asks: IF this process were centered, would its natural spread fit inside the spec limits? It compares the spec width to six standard deviations of the process |
| 4 | [Process Capability (Cpk)](process_capability_cpk.md) | Intermediate | Cpk is Cp's honest sibling: it also checks where the process is actually centered |
| 5 | [X-Bar Control Chart](x_bar_chart.md) | Intermediate | The X-bar chart tracks the AVERAGE of small samples over time and draws control limits around it |
| 6 | [R Control Chart](r_chart.md) | Intermediate | The R chart tracks the RANGE (biggest minus smallest) within each sample - it watches the process's consistency, while the X-bar chart watches its average |
| 7 | [P Control Chart](p_chart.md) | Intermediate | The p chart tracks the PROPORTION of defective items in samples - perfect for pass/fail data like '3 of 100 deliveries late' |

Reinforce what you learned:

- Flashcard deck: [flashcards/flashcards_quality.md](../../flashcards/flashcards_quality.md)
- Recall drill: [drills/drill_quality.md](../../drills/drill_quality.md)
