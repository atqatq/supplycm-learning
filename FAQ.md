---
title: "Supply Chain Management FAQ | Frequently Asked Questions"
description: "Answers to common supply chain questions. Learn about forecasting, inventory, quality, lean, and more."
keywords: "supply chain FAQ, frequently asked questions, SCM help, supply chain basics, operations management"
---

# Frequently Asked Questions

## Getting Started

### Q: Do I need to know Python to use these lessons?

A: Basic Python helps (variables, lists, functions). If you are new to Python, try a free online tutorial first.

### Q: Do I need to install supplycm?

A: Yes. Run `pip install supplycm` in your terminal.

### Q: What if I get an error importing supplycm?

A: Check that you installed it correctly: `pip show supplycm`. If not installed, run `pip install supplycm`.

## Understanding Concepts

### Q: What is the difference between forecasting and planning?

A: Forecasting is predicting what will happen. Planning is deciding what to do about it. You forecast demand, then plan production.

### Q: Why are there so many forecasting methods?

A: Different methods work for different situations. Naive is simplest. Moving average smooths noise. Exponential smoothing tracks trends. Holt-Winters handles seasonality. Croston handles intermittent demand.

### Q: What is the difference between EOQ and safety stock?

A: EOQ tells you how much to order. Safety stock tells you how much extra to keep for protection.

### Q: Why not just order a huge amount to never run out?

A: Because holding inventory costs money (storage, insurance, spoilage). EOQ finds the balance.

### Q: What is the difference between Cp and Cpk?

A: Cp measures if your process spread fits within specs. Cpk also checks if it is centered. Cpk is always less than or equal to Cp.

### Q: What is the bullwhip effect?

A: Small changes in customer demand cause bigger changes upstream. A 5% increase in customer demand might cause 20% increase in factory orders.

## Using supplycm

### Q: How do I know which function to use?

A: Check the [algorithm selector](https://github.com/atqatq/supplycm/blob/main/docs/ALGORITHM_SELECTOR.md) in the main supplycm repo.

### Q: Can I use supplycm without these lessons?

A: Yes. The lessons explain the concepts. The supplycm package has docstrings with examples in every function.

### Q: Do I need to be good at math?

A: Basic arithmetic is enough. The formulas look complex but the ideas are simple. The lessons explain everything in plain English.

### Q: Can I use supplycm for real business decisions?

A: Yes. The algorithms are standard supply chain methods used by professionals. But always validate with your own data and judgment.

## Common Mistakes

### Q: My forecast is always wrong. What am I doing wrong?

A: Forecasts are never perfect. The goal is to be less wrong. Try different methods, check MAPE, and use the one that works best for your data.

### Q: My EOQ seems too large. Is something wrong?

A: Check your inputs. Make sure demand is annual (not monthly), holding cost is per year (not per month), and units are consistent.

### Q: My OEE is 60%. Is that bad?

A: 60% is typical. World class is 85%. Look at which component is lowest (availability, performance, or quality) and improve that first.

### Q: I do not understand Little's Law. Help?

A: It says: the stuff in progress equals the rate of production times the time each unit takes. If you make 10 per hour and each takes 5 hours, you have 50 in progress. Simple as that.

## The Algorithm Library

### Q: What is the algorithm library?

A: A plain-English page for every algorithm in the supplycm package - all 397 of them. Each page has a runnable example, three self-check questions, and a small challenge. (One exception, stated openly: `closeness_centrality` is a reserved stub in supplycm v1.2.1, so its page teaches the concept with a pure-Python stand-in.) Start at [algorithms/README.md](algorithms/README.md).

### Q: Do I have to learn all 397 algorithms?

A: No. The [6-month program](SIX_MONTH_PLAN.md) sequences the ones that matter most; the tracker lets you check off what you master. Many professionals use the library as a reference and study 100-150 pages deeply.

### Q: Can I really understand them without math?

A: Yes - that is the point of the library. Every page explains the idea in everyday words, shows a small worked example, and labels the difficulty. The only arithmetic used is +, -, x, and division.

## Next Steps

### Q: I finished all 12 modules. What now?

A: Try the [exercises](exercises/), take the [final exam](quizzes/quiz_12_final.md), and read the [real-world examples](examples/).

### Q: Where can I learn more?

A: Read the supplycm [documentation](https://github.com/atqatq/supplycm). Try the [Jupyter notebooks](https://github.com/atqatq/supplycm/tree/main/notebooks) in the main repo.

### Q: How can I contribute?

A: If you find a mistake or have an idea for a new lesson, open an issue or pull request on [GitHub](https://github.com/atqatq/supplycm-learning).
