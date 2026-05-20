---
title: "Recall Drill: Traceability & Blockchain | supplycm Learning"
description: "Active-recall drill with answer key covering all 4 supplycm traceability & blockchain algorithms."
keywords: "drill, recall, blockchain, supply chain practice"
---

# Recall Drill: Traceability & Blockchain

Answer from memory first, then check the key at the bottom.
Score 1 point per correct answer. Anything you miss goes back on your flashcard rotation.

## Part 1 - Questions

**Hash Chain** (`hash_chain`)

1. Why does including the previous hash make tampering visible?
2. What is a 'fingerprint' (hash) here?
3. What does a hash chain NOT protect?

**Chain Verification** (`verify_chain`)

4. What does verification actually recompute?
5. Verification passes. What have you proven - and not proven?
6. Where should the chain's root be anchored for real trust?

**Provenance Tracking** (`provenance_tracking`)

7. Why is provenance critical during recalls?
8. What makes a provenance trail credible?
9. How does this connect to blockchain thinking?

**Smart Contract Check** (`smart_contract_check`)

10. What makes a contract 'smart'?
11. What's the danger of overly strict automated rules?
12. Who must trust what here?

Total: 12 questions.

## Part 2 - Answer key

1. Editing record 2 changes its hash, which no longer matches what record 3 embedded - the break cascades to the end.
2. A short digital summary of the data - change one letter in the data and the fingerprint changes completely.
3. The first record and the system writing it - trust still anchors at the origin and at who controls the keys.
4. Every hash from the raw records, chaining each into the next - a full re-derivation, not a spot check.
5. That records match the chain as given - not that the events truly happened; authenticity of the FIRST record is a separate trust question.
6. In something independent - published checkpoints, multiple custodians - so rewriting history requires rewriting the world, not just your database.
7. Scope: you recall the exact affected batches and destinations - not everything, not too little; precision saves money and trust.
8. Every event anchored at its time and place, ideally hash-chained or third-party witnessed - unanchored stories are just stories.
9. Blockchain is one way to make the trail tamper-evident; provenance is the QUESTION, chain structures are one ANSWER.
10. Self-execution: rules evaluate automatically on data, and consequences (release, reject, alert) follow without human mediation.
11. Rigidity - real life has edge cases; good smart contracts pair hard rules with a documented exception path.
12. Both sides trust the rule code and the data feed - which is why sensor integrity and rule transparency come before automation.

**Scoring:** 90%+ = move on · 70-89% = review misses · below 70% = reread the module library pages.
