# Contributing to CTG Model

Thank you for your interest in contributing to the CTG framework. This project thrives on adversarial review — the best contributions have been attacks on the framework's weaknesses.

## How to Contribute

### 1. Attack the Framework (Most Valuable)

Open an Issue with the tag `[ATTACK]` and describe:
- **Which section** you're attacking (e.g., "§3.3 DDI Behavior Envelope")
- **The logical argument** for why it fails
- **An extreme example** that breaks the framework
- **Optional: A proposed fix**

The framework evolved from v1.0 to v3.2 through exactly this process. Every major structural change was driven by a specific adversarial attack.

### 2. Apply CTG to a Real System

Open an Issue or PR with the tag `[CASE-STUDY]`:
- Pick a real AI product (e.g., a specific medical AI, trading algorithm, recommendation system)
- Classify it using CTG coordinates: [C?, T?, G?]
- Document any difficulties or ambiguities you encountered
- This helps us find where the framework's definitions are too vague

### 3. Improve Definitions

Submit a PR with the tag `[DEFINITION]`:
- Tighten vague language
- Add formal definitions where concepts are only described informally
- Propose testable criteria for levels that currently lack them

### 4. Translate

Submit a PR with the tag `[TRANSLATION]`:
- The original whitepaper is in Chinese; English version is available
- Improvements to the English version welcome
- Other languages welcome

### 5. Legal/Policy Review

Open an Issue with the tag `[LEGAL]`:
- How does CTG interact with your jurisdiction's AI regulations?
- Does the responsibility allocation table hold up under your legal system?
- What would need to change for CTG to be adopted by regulators?

### 6. Build Tools

Submit a PR with the tag `[TOOL]`:
- CTG Evaluator: input AI system description → output (C, T, G) rating
- DDI monitoring dashboard
- Behavior Envelope definition toolkit

## Style Guide

- Be precise. "This is wrong because X, here's a counterexample" > "I don't like this"
- Be constructive. Attacks are welcome; attacks with proposed fixes are more welcome
- Reference specific sections (e.g., "§3.2 Standard Contestor definition")
- If proposing changes, explain what problem the change solves

## Languages

- Issues and discussions: Chinese or English
- Whitepaper source: Chinese (original), English (available)
- Code and tools: English

## Code of Conduct

- Engage in good faith
- Attack ideas, not people
- Assume the best intentions
- Cite sources when making empirical claims
