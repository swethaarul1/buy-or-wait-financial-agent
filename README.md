# Buy or Wait? — Financial Affordability Agent

A reliability-first AI financial agent for the HackerRank Orchestrate September 2026 challenge.

## Goal

Given a purchase request and supporting financial data, determine whether the user can safely pay now, use a payment plan, wait, or not proceed — while respecting the challenge's financial constraints and producing the required `output.csv` schema.

## Design principle

**AI extracts and interprets unstructured evidence. Deterministic code calculates money, simulates cash flow, validates plans, and makes the final constrained decision.**

This separation is intentional: financial calculations must be reproducible, testable, and resistant to hallucination.

## Planned pipeline

```text
requests.csv + financial data + messages/images
                    |
                    v
             Evidence extraction
                    |
                    v
             Evidence reconciliation
                    |
                    v
             Normalized financial state
                    |
                    v
             Cash-flow simulation
                    |
                    v
             Candidate plan generation
                    |
                    v
             Plan validation + ranking
                    |
                    v
              Decision + explanation
                    |
                    v
                 output.csv
```

## Repository structure

```text
code/          Production agent implementation
tests/         Unit, regression, and adversarial tests
evaluation/    Local evaluation and stress testing
prompts/       LLM/VLM extraction prompts
docs/          Architecture and AI-judge notes
```

## Running the agent

The intended challenge entry point is:

```bash
python3 code/main.py
```

The challenge dataset itself should remain outside this repository and outside the final HackerRank code ZIP where the challenge instructions require exclusion.

## Status

🚧 Initial architecture and repository skeleton — implementation in progress.
