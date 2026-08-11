# ADR-014 — Workflows as Explicit Organizational State Machines

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization requires repeatable processes that coordinate
deterministic systems, autonomous Agents, humans, Decisions, Artifacts
and Events.

Representing organizational processes as free-form agent conversations
would create weak state management, poor auditability and unnecessary
coordination overhead.

## Decision

Reusable organizational processes will be represented through versioned
Workflow Definitions.

A Workflow defines:

- triggers;
- states;
- steps;
- dependencies;
- parallelism;
- transitions;
- decision gates;
- human approvals;
- policy checks;
- failure handling;
- timeout behavior;
- termination conditions.

Workflow states describe organizational process state rather than
individual Agent activity.

## Execution Modes

Workflow Steps may be:

- deterministic;
- agentic;
- human;
- hybrid.

Agentic execution should only be used when reasoning provides material
value.

## Agent Selection

Workflow Definitions should generally request capabilities rather than
bind permanently to specific Agents or model providers.

Agent routing and model routing remain runtime responsibilities.

## Decision Gates

Material organizational Decisions must remain explicit canonical
Decision entities.

A Workflow may coordinate a Decision Gate but must not silently treat
an Agent recommendation as a committed Decision.

## Events

Workflows may be triggered by Events and may emit Events as state
transitions occur.

Event data must remain separate from routing logic.

## Human Participation

Human approval and intervention are first-class Workflow Steps rather
than implicit conversational side effects.

## Tool Access

Workflow progression does not itself grant tool authority.

Tool use remains subject to Policy enforcement, Agent authority,
Task authority and tool permissions.

## Consequences

The organization can now represent repeatable and auditable processes
without requiring persistent Agent conversations.

Future implementation may use state machines, DAG engines, event-driven
workflow systems or equivalent execution technologies without changing
the organizational semantics.