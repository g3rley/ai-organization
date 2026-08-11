# ADR-006 — Separation of Task Intent and Execution Runs

Status: Accepted
Date: 2026-08-11

## Context

A unit of organizational work may require multiple execution attempts,
different models, different agents or different tools before completion.

Treating a Task and its execution as the same entity would make it difficult
to represent retries, failures, routing, cost and comparative performance.

## Decision

Task and Run will be separate canonical entities.

A Task defines:

- organizational purpose;
- execution mode;
- inputs;
- expected outputs;
- dependencies;
- completion criteria;
- authority boundaries;
- execution limits.

A Run represents one concrete attempt to execute a Task.

Prompts and model calls are implementation details of Runs and are not
canonical Task definitions.

## Rationale

Separating Task from Run enables:

- retries;
- model routing;
- agent routing;
- cost accounting;
- failure analysis;
- parallel execution;
- reproducibility;
- evaluation;
- observability.

## Consequences

A single Task may have zero, one or many Runs.

Task completion must not be inferred solely from a successful model response.

Completion depends on the Task's explicit completion criteria.

Execution logs, tool calls, model identity, token consumption and runtime
errors belong primarily to Runs rather than Tasks.