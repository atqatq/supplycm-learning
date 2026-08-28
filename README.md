# Learn Supply Chain Management - Free Course with Python

> A complete, free course that teaches supply chain management from the ground up. Learn forecasting, inventory management, logistics, lean manufacturing, Six Sigma quality, and more. Includes Python code examples, interactive Jupyter notebooks, exercises, and quizzes.

[![Python 3.6+](https://img.shields.io/badge/python-3.6+-blue.svg)](https://www.python.org/downloads/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Free Course](https://img.shields.io/badge/course-free-success.svg)](https://github.com/atqatq/supplycm-learning)
[![Beginner Friendly](https://img.shields.io/badge/beginner-friendly-green.svg)](https://github.com/atqatq/supplycm-learning)

## What You Will Learn

This course teaches you how to manage a supply chain step by step. You will learn:

- **Demand forecasting** - predict what customers will buy using moving averages, exponential smoothing, and seasonal models
- **Inventory management** - calculate optimal order quantities (EOQ), safety stock, and reorder points
- **Supplier management** - choose suppliers using AHP, TOPSIS, and the Kraljic matrix
- **Warehouse operations** - organize storage, plan picking routes, and optimize layouts
- **Transportation and routing** - solve the Traveling Salesman Problem (TSP) and Vehicle Routing Problem (VRP)
- **Quality control** - apply Six Sigma, calculate DPMO, and use control charts
- **Lean manufacturing** - calculate takt time, OEE, and apply Little's Law
- **Sales and Operations Planning (S&OP)** - balance supply and demand
- **Supply chain contracts** - revenue sharing, buyback, and quantity flexibility contracts
- **Sustainability** - calculate carbon footprint and manage reverse logistics

## Who This Course Is For

- **Students** studying supply chain management, operations, or logistics
- **Career changers** who want to become supply chain professionals
- **Working professionals** who need to use Python for supply chain analysis
- **Anyone** who wants to understand how products get from factory to customer

## What Makes This Course Different

1. **Plain English explanations** - no confusing jargon or heavy math
2. **Python code examples** - every concept includes runnable code using the [supplycm](https://github.com/atqatq/supplycm) package
3. **Interactive notebooks** - learn by doing with Jupyter notebooks
4. **Real-world examples** - coffee shops, toy stores, bakeries, and more
5. **Practice exercises** - 12 exercises with answers
6. **Self-test quizzes** - check your understanding after each module
7. **Completely free** - open source, MIT licensed

## The Algorithm Library

We are writing a plain-English page for EVERY algorithm in the
[supplycm package](https://github.com/atqatq/supplycm). Over 290 pages are
done - forecasting, the inventory toolbox, MRP, and scheduling are complete,
and the network, routing, and optimization libraries are landing now. Each page
has a runnable example, three self-check questions, and a challenge.

Browse the library: [algorithms/](algorithms/README.md) - track your progress
with the [tracker](progress/ALGORITHM_TRACKER.md). A full six-month guided
program is taking shape in [SIX_MONTH_PLAN.md](SIX_MONTH_PLAN.md).

## Quick Start

```bash
# Install the supplycm package
pip install supplycm

# Clone this learning repo
git clone https://github.com/atqatq/supplycm-learning.git
cd supplycm-learning

# Start with Module 1
open modules/01_what_is_supply_chain.md
```

## Course Contents

### Module 1: Supply Chain Basics
[What is a Supply Chain?](modules/01_what_is_supply_chain.md) | [Notebook](notebooks/01_supply_chain_basics.ipynb)

Learn what a supply chain is, the 5 steps (Plan, Source, Make, Deliver, Return), and why supply chain management matters.

### Module 2: Demand Forecasting
[Predicting the Future](modules/02_forecasting.md) | [Notebook](notebooks/02_forecasting.ipynb)

Learn demand forecasting methods: naive forecast, simple moving average (SMA), exponential smoothing, Holt-Winters for seasonality, and Croston's method for intermittent demand. Includes forecast accuracy metrics like MAPE.

### Module 3: Inventory Management
[Having the Right Amount of Stuff](modules/03_inventory.md) | [Notebook](notebooks/03_inventory.ipynb)

Master inventory management: Economic Order Quantity (EOQ), safety stock calculation, reorder points, ABC analysis, and the newsvendor model for perishable goods.

### Module 4: Supplier Management
[Working with Suppliers](modules/04_suppliers.md) | [Notebook](notebooks/07_suppliers.ipynb)

Learn supplier selection methods: Analytic Hierarchy Process (AHP), TOPSIS, the Kraljic supplier segmentation matrix, and supplier performance measurement.

### Module 5: Warehouse Management
[Storing Stuff](modules/05_warehouses.md) | [Notebook](notebooks/08_warehouses.ipynb)

Learn warehouse operations: ABC slotting, order picking routes, cross-docking, pallet building, and warehouse layout optimization.

### Module 6: Transportation and Routing
[Moving Stuff Around](modules/06_transportation.md) | [Notebook](notebooks/06_transportation.ipynb)

Solve routing problems: Traveling Salesman Problem (TSP), Vehicle Routing Problem (VRP), nearest neighbor heuristic, 2-opt improvement, and the Hungarian algorithm for assignment.

### Module 7: Quality Control and Six Sigma
[Making Good Stuff](modules/07_quality.md) | [Notebook](notebooks/04_quality.ipynb)

Learn quality management: Six Sigma methodology, DPMO (Defects Per Million Opportunities), process capability (Cp and Cpk), control charts, and the DMAIC improvement process.

### Module 8: Lean Manufacturing
[Working Smart](modules/08_lean.md) | [Notebook](notebooks/05_lean.ipynb)

Master lean principles: takt time, Overall Equipment Effectiveness (OEE), Little's Law, cycle time efficiency, the 8 wastes (DOWNTIME), and 5S methodology.

### Module 9: Sales and Operations Planning
[Planning Ahead](modules/09_planning.md) | [Notebook](notebooks/09_sop.ipynb)

Learn S&OP: demand-supply matching, chase production strategy, level production strategy, and the monthly S&OP cycle.

### Module 10: Supply Chain Contracts
[Making Deals](modules/10_contracts.md) | [Notebook](notebooks/10_contracts.ipynb)

Understand supply chain contracts: revenue sharing, buyback contracts, quantity flexibility, and double marginalization.

### Module 11: Sustainability
[Being Green](modules/11_sustainability.md) | [Notebook](notebooks/11_sustainability.ipynb)

Learn green supply chain practices: carbon footprint calculation, reverse logistics, energy consumption, and the three R's (Reduce, Reuse, Recycle).

### Module 12: Complete Example
[Putting It All Together](modules/12_putting_it_together.md) | [Notebook](notebooks/12_complete_example.ipynb)

Apply everything to a real business: a complete coffee shop supply chain walkthrough using all 12 modules.

## Learning Resources

### Interactive Jupyter Notebooks
12 notebooks with runnable Python code: [notebooks/](notebooks/)

### Detailed Sub-Lessons
Step-by-step breakdowns of complex topics: [sub-lessons/](sub-lessons/)

### Practice Exercises
12 exercises with problems and answers: [exercises/](exercises/)

### Self-Test Quizzes
12 quizzes plus a final exam: [quizzes/](quizzes/)

### Real-World Examples
- [Coffee Shop Supply Chain](examples/coffee_shop.md)
- [Online Toy Store](examples/toy_store.md)
- [Bakery Operations](examples/bakery.md)
- [T-Shirt Business](examples/tshirt_business.md)
- [Bicycle Shop](examples/bicycle_shop.md)

### Reference Materials
- [Glossary](glossary.md) - definitions of all supply chain terms
- [Cheat Sheet](cheatsheet.md) - quick formula reference in Python notation
- [FAQ](FAQ.md) - frequently asked questions

## Recommended Learning Path

| Week | Focus | Modules |
|------|-------|---------|
| 1 | Basics + Forecasting | Modules 1-2 |
| 2 | Inventory + Suppliers | Modules 3-4 |
| 3 | Warehouses + Transportation | Modules 5-6 |
| 4 | Quality + Lean | Modules 7-8 |
| 5 | Planning + Contracts | Modules 9-10 |
| 6 | Sustainability + Integration | Modules 11-12 |
| 7 | Practice | Exercises and quizzes |
| 8 | Apply | Real-world examples and final exam |

## Skills You Will Gain

After completing this course, you will be able to:

- Forecast demand using multiple methods
- Calculate optimal inventory levels (EOQ, safety stock, reorder points)
- Evaluate and select suppliers systematically
- Design efficient warehouse layouts
- Plan delivery routes that minimize distance
- Measure quality using Six Sigma metrics
- Apply lean principles to improve operations
- Run an S&OP cycle
- Design supply chain contracts
- Assess environmental impact
- Use Python for supply chain analysis

## Prerequisites

- **Python basics**: variables, lists, functions (a 1-hour online tutorial is enough)
- **No supply chain experience needed**: we start from zero
- **No math background needed**: all formulas use simple Python notation

## Tools Used

- **[supplycm](https://github.com/atqatq/supplycm)** - free Python package with 397 supply chain algorithms
- **[Jupyter Notebook](https://jupyter.org/)** - for interactive learning
- **Python 3.6 or later**

## Community

- **[Discussions](https://github.com/atqatq/supplycm-learning/discussions)** - Ask questions, share ideas, introduce yourself
- **[Issues](https://github.com/atqatq/supplycm-learning/issues)** - Report mistakes or suggest improvements
- **[Contributing Guide](CONTRIBUTING.md)** - Help improve these lessons

### Ways to Contribute

We welcome contributions of all sizes! Look for issues labeled `good first issue` for beginner-friendly tasks:

- **Translations** - Help translate lessons to Spanish, Chinese, French, and more
- **Real-world examples** - Add case studies from pharmacy, restaurant, manufacturing
- **Visualizations** - Create diagrams and charts to explain concepts
- **Exercises and quizzes** - Add practice problems
- **Notebooks** - Create interactive Jupyter notebooks
- **Documentation** - Fix typos, improve explanations, expand FAQ

See [open issues](https://github.com/atqatq/supplycm-learning/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22) for ideas.

## Related Resources

- **[supplycm Python package](https://github.com/atqatq/supplycm)** - The library used in these lessons
- **[supplycm on PyPI](https://pypi.org/project/supplycm/)** - Install with `pip install supplycm`

## License

MIT - see [LICENSE](LICENSE). Free to use, modify, and share.

## Keywords

supply chain management, SCM, logistics, demand forecasting, inventory management, EOQ, safety stock, reorder point, ABC analysis, supplier management, AHP, TOPSIS, Kraljic matrix, warehouse management, order picking, cross-docking, transportation, routing, TSP, VRP, vehicle routing, traveling salesman, assignment problem, Hungarian algorithm, quality control, Six Sigma, DPMO, Cp, Cpk, control charts, DMAIC, lean manufacturing, takt time, OEE, Little's Law, 8 wastes, 5S, S&OP, sales and operations planning, chase strategy, level strategy, supply chain contracts, revenue sharing, buyback contract, quantity flexibility, double marginalization, sustainability, carbon footprint, reverse logistics, Python, operations management, operations research, free course, tutorial, beginner friendly
