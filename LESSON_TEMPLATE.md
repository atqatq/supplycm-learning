# Lesson Template and Style Guide

Every lesson in this repo - core modules and algorithm library pages - follows
the same skeleton. Consistency lowers the cost of learning; surprises belong in
the content, not the format.

## The skeleton

```markdown
---
title: "<Topic> | supplycm Learning"
description: "<One sentence, includes the key terms learners search for.>"
keywords: "<comma-separated search terms>"
---

# <Title>

<The plain-English explanation. Short sentences. An everyday analogy within
the first two paragraphs. No symbol the reader hasn't met yet.>

## Try it with supplycm

```python
<exact import path>
<complete, runnable example>
```

<What the output means, in one or two sentences.>

## Check yourself

1. <Question answered from memory>
2. <Question>
3. <Question>

<details>
<summary>Show answers</summary>
...
</details>

## Try this now

<A small challenge the learner does with their own numbers or business.>
```

## Voice rules

- Second person ("you"), present tense, active voice.
- Sentences under 20 words where possible.
- Everyday analogies are mandatory: bakery, cafe, toy store, workshop.
- Any number the learner must compute is small enough to check by hand.
- Never introduce a term without defining it at first use; add it to the
  [glossary](glossary.md) too.
- Humor allowed; sarcasm and idioms that translate poorly are not.

## Code rules

- The example runs EXACTLY as printed. If it cannot run, it does not ship.
- Import lines are complete and correct (`from supplycm.inventory import eoq`).
- Show the output (or describe it precisely) after every example.
- Seed any randomness so results are reproducible.
- Numbers in examples: small enough to verify by hand.

## Difficulty labels

- **Beginner** - needs Module 1-3 only
- **Intermediate** - needs the module's core lesson
- **Advanced** - needs two or more concepts combined; say which

## The no-math rule

Allowed: +, -, ×, ÷, percentages, sorting, counting, comparing.
Not allowed: calculus notation, matrix algebra symbols, formal proofs.
If a method needs more, explain it as a recipe ("the computer tries, keeps the
best, repeats") and link the function signature.
