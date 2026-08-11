# ADR-001 — Separation of Intelligence and Organizational State

Status: Accepted
Date: 2026-08-11

## Context

The organization will use multiple language models, interfaces,
agents and potentially multiple model providers.

Model conversations and provider-native memory cannot guarantee
canonical, portable or fully auditable organizational state.

## Decision

Language models will not be authoritative stores of organizational state.

Persistent state will reside in infrastructure external to individual models.

Models will access the appropriate state through controlled context,
tools, APIs or MCP resources.

## Consequences

### Positive

- model-provider independence;
- consistent shared state;
- auditability;
- version control;
- easier multi-model operation;
- controlled memory;
- future MCP integration.

### Negative

- additional infrastructure;
- synchronization requirements;
- explicit state-management design is required.

## Alternatives Rejected

### Model-native memory as canonical state

Rejected because it creates provider dependence and weakens
auditability and cross-model consistency.

### Conversation history as organizational memory

Rejected because conversations are unstructured, incomplete and
poorly suited to canonical state management.