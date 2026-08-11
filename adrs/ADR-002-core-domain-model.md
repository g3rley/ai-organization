# ADR-002 — Canonical Organizational Domain Model

Status: Accepted
Date: 2026-08-11

## Decision

The AI Organization will use explicit canonical entities for:

- Organization
- Project
- Objective
- Task
- Run
- Agent Definition
- Artifact
- Claim
- Evidence
- Decision
- Event
- Memory Record
- Workflow Definition
- Policy
- Evaluation
- Lesson

Conversation messages and prompts are not canonical organizational entities.

## Rationale

The organization requires a model-independent representation of work,
state, evidence, execution and governance.

This domain model will serve as the semantic foundation for:

- schemas;
- databases;
- APIs;
- MCP resources and tools;
- orchestration;
- observability;
- evaluations.

## Consequence

Implementation technologies may change without changing the semantic
model of the organization.