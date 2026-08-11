# ADR-016 — Capability-Based Agent Registry

Status: Accepted
Date: 2026-08-11

## Context

The organization now possesses a canonical Agent Contract but requires
an initial portfolio of reusable Agent Definitions.

Directly mapping every traditional organizational job title to a separate
Agent would create unnecessary specialization, coordination cost and
routing complexity.

The organization also requires a mechanism for locating suitable Agents
without binding Workflows and Tasks to specific roles or model providers.

## Decision

The organization will maintain a canonical Agent Registry.

The Registry will contain:

- a catalog of organizational capabilities;
- registered Agent Definitions;
- Agent classes;
- Agent Contract references;
- activation characteristics.

Task routing should normally be capability-based rather than title-based.

## Initial Portfolio

The initial portfolio will remain intentionally compact.

Capabilities that can be adequately combined within one autonomous
reasoning boundary will not initially receive separate Agents.

Examples include:

- backend and frontend implementation under Software Engineer;
- sales and customer success under Growth Strategy;
- preliminary privacy, compliance and regulatory triage under
  Security, Privacy and Risk;
- QA primarily through deterministic Evaluations and testing Workflows.

These responsibilities may later be separated when operational Evidence
demonstrates a meaningful specialization benefit.

## Agent Classes

Agents are classified as:

- core;
- specialist;
- ephemeral.

Registration does not imply continuous execution.

Agents remain inactive unless explicitly activated by organizational work.

## Model Independence

The Registry does not bind Agent Definitions to individual model providers.

Model selection remains a runtime responsibility based on Agent requirements,
Task characteristics, historical Evaluations, cost and latency.

## Routing

Future Agent routing may consider:

- required capability match;
- authority;
- Project constraints;
- Agent status;
- historical performance;
- cost;
- latency;
- risk.

## Organizational Complexity

A new Agent should be introduced only when its expected increase in
organizational capability exceeds the additional coordination cost it creates.

## Consequences

The organization now possesses a bounded initial Agent portfolio suitable
for constructing real Agent Contracts and Workflows.

Future specialization decisions can be made using execution and Evaluation
data rather than organizational intuition alone.