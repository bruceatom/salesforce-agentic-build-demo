# Salesforce Agentic Build Demo

A small proof of concept for specification-driven, agentic Salesforce development.

The project demonstrates a controlled workflow:

**Product Requirements Document → Build Specification → AI Agent → Salesforce Source → Scratch Org → Validation → Human Gates**

## What This Demonstrates

The repository separates product requirements, implementation decisions, agent instructions, and acceptance gates before build execution.

The demo implements a small Salesforce change using source-format metadata and validates the result in a disposable scratch org.

The workflow emphasizes:

- traceability from requirements to Salesforce metadata;
- declarative-first implementation;
- explicit human approval gates;
- machine correctness **and** human usability;
- observable build and validation results;
- permission sets rather than profile changes;
- human control over release and irreversible actions.

## Scope

This is intentionally a small demonstration, not a production managed package.

Package promotion, AppExchange submission, Security Review, and production deployment are outside the scope of this repository.
