# ADR-021 — Manual Runtime Before Automation

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization now possesses sufficient organizational semantics to
execute a complete Startup Discovery Workflow.

Automating orchestration, persistence, context compilation and MCP access
before executing a real organizational process would risk encoding flawed
assumptions into infrastructure.

The organization therefore requires an integration phase in which the
architecture is exercised manually.

## Decision

The first complete organizational execution environment will be a Manual
Organization Runtime.

Humans will temporarily perform runtime responsibilities including:

- Workflow progression;
- Task materialization;
- capability routing;
- model selection;
- context compilation;
- persistence;
- validation;
- approval;
- escalation supervision.

Language models will execute bounded Runs.

They will not serve as canonical organizational state.

## Temporary State Store

Non-sensitive prototype operational state may temporarily be persisted as
versioned YAML records under Git.

This mechanism is an implementation adapter for the prototype and does not
change the architectural separation between intelligence and state.

Production operational state is expected to move to dedicated database and
Artifact storage systems.

## Model Execution

Each model invocation should correspond to a bounded Run.

The Agent Definition remains independent from the selected model provider.

The Run records which model actually executed the work.

## Context

Manual context compilation should include only the information materially
relevant to the current Task.

Conversation history is not considered authoritative organizational state.

## Proposed State

Model responses represent proposed organizational changes.

A response does not become canonical state merely because a model generated
it.

Proposed outputs must pass applicable:

- schemas;
- referential checks;
- Policies;
- Evaluation requirements;
- authority requirements.

## Auditability

Manual Run context manifests and optional raw responses may be preserved for
debugging and reproducibility.

Supporting execution files remain distinguishable from canonical
organizational entities.

## Security

Secrets, credentials and restricted personal or clinical information must not
be stored in the Git-backed manual state layer.

The manual healthcare-related prototype should use public, synthetic or
appropriately de-identified information until dedicated secure data controls
exist.

## Purpose

The Manual Runtime is an organizational integration test.

Its purpose is to discover problems in:

- schemas;
- Agent Contracts;
- Workflow Definitions;
- Policies;
- Evaluations;
- Artifact interfaces;
- routing;
- context requirements;

before these semantics are implemented as persistent automation.

## Exit Criterion

Major runtime automation should begin only after at least one real Project
successfully executes the intended end-to-end Workflow using canonical
organizational state.

## Consequences

The next milestone is no longer another architecture document.

The next milestone is the first real Project executed through the AI
Organization.