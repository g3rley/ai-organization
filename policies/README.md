# Policy System

Version: 0.1.0

## Effective Authority

Organizational authority is restrictive by composition.

Lower organizational layers may reduce authority but may not
increase authority denied by a higher layer.

The initial precedence hierarchy is:

1. Constitution
2. Hard Guardrails
3. Organization Policies
4. Project Constraints and Autonomy
5. Workflow Constraints
6. Agent Contract
7. Task Authority
8. Tool Permissions

## Restriction Ordering

For permission-like decisions, the initial restriction order is:

allow
< propose_only
< require_approval
< deny

When multiple applicable rules conflict, the most restrictive
valid rule prevails unless an explicitly authorized Policy override exists.

## Deny by Default

Absence of explicit authorization should not be interpreted as permission
for materially consequential external actions.

## Scope

A lower-level object may restrict an inherited permission.

It may not grant a permission unavailable at a higher level.

## Policy Evaluation

Policies should be evaluated at relevant enforcement points rather than
only when an Agent is initially activated.

Examples include:

- before Task assignment;
- before a Run;
- before a Tool call;
- before committing a Decision;
- before publishing an Artifact;
- before persistent Memory writes.

## Fail Closed

Security, privacy, financial and other high-impact policies should normally
fail closed when Policy evaluation cannot be completed.

## Overrides

Overrides must be explicit, limited in scope, attributable and auditable.

An override must never silently mutate the original Policy.