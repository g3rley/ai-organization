# ADR-007 — Run as an Auditable Execution Attempt

Status: Accepted
Date: 2026-08-11

## Context

Tasks represent organizational intent but do not describe what occurred
during execution.

A Task may require multiple attempts, different executors, different models,
different tools or different runtime configurations before satisfying its
completion criteria.

The organization requires sufficient execution history for observability,
cost accounting, evaluation and continuous improvement.

## Decision

Each concrete attempt to execute a Task will be represented as a Run.

A Run may record:

- executor;
- agent definition;
- runtime configuration;
- relevant context snapshot;
- model calls;
- tool calls;
- outputs;
- resource consumption;
- evaluation results;
- termination reason;
- timing information.

A Run may contain multiple model calls and tool calls.

Successful Run execution does not by itself imply successful Task completion.

## Rationale

Explicit Runs enable:

- retry analysis;
- model routing;
- tool observability;
- agent evaluation;
- cost accounting;
- latency analysis;
- reproducibility;
- failure diagnosis;
- comparison between execution strategies;
- organizational learning.

## Security

Run records must not become uncontrolled repositories of secrets or
sensitive information.

Sensitive context should preferably be referenced through controlled
resources rather than duplicated into execution logs.

## Consequences

The organization will generate substantially more execution metadata.

Storage, retention and privacy policies will therefore be required.

Execution history will be separable from organizational intent and
canonical work products.