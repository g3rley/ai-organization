# ADR-012 — Policy-Based Authority Enforcement

Status: Accepted
Date: 2026-08-11

## Context

Projects, Agents, Tasks, Workflows and Tools may all declare permissions
or constraints.

Without an explicit authority hierarchy, conflicting declarations could
allow lower-level components to grant themselves privileges prohibited
by higher-level governance.

The organization requires deterministic and auditable enforcement.

## Decision

Organizational authority will be constrained through versioned Policies.

Lower-level components may restrict inherited authority but may not expand
authority denied or unavailable at a higher level.

The initial authority hierarchy is:

1. Constitution
2. Hard Guardrails
3. Organization Policies
4. Project Constraints and Autonomy
5. Workflow Constraints
6. Agent Contract
7. Task Authority
8. Tool Permissions

For permission-like outcomes, the initial restriction ordering is:

allow
< propose_only
< require_approval
< deny

The most restrictive applicable valid rule prevails unless an explicit
authorized override mechanism exists.

## Enforcement Classes

Policies may be classified as:

- hard;
- controlled override;
- advisory.

Hard Policies cannot be bypassed through normal Agent, Task, Workflow
or Project authority.

## Enforcement Points

Policy evaluation may occur at multiple execution boundaries including:

- Task creation;
- Task assignment;
- Run initialization;
- model invocation;
- Tool invocation;
- Decision commitment;
- Artifact publication;
- persistent Memory writes.

Authorization of a Run does not imply authorization of every action
performed inside that Run.

## Fail-Closed Principle

Security, privacy, financial and similarly high-impact Policy evaluation
should normally fail closed.

Failure to evaluate authorization must not silently become authorization.

## Overrides

Overrides must be:

- explicit;
- attributable;
- bounded;
- time-limited when practical;
- auditable.

Overrides must not silently modify the underlying Policy.

## Model Independence

Critical Policy enforcement should not depend solely on language-model
compliance.

Policies may be expressed to models for reasoning purposes, but material
enforcement should eventually occur through deterministic control points.

## Consequences

The organization will require a future Policy Engine or equivalent
enforcement layer.

MCP gateways and orchestration components may act as Policy Enforcement
Points.

Policy evaluation decisions themselves should eventually be observable
and auditable.