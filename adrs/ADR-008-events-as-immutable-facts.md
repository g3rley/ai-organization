# ADR-008 — Events as Immutable Organizational Facts

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization will eventually require asynchronous workflows,
external integrations, automated monitoring and selective activation
of agents.

Continuous direct communication between agents would introduce
unnecessary coordination cost and coupling.

The organization therefore requires a canonical representation of
relevant occurrences.

## Decision

Relevant occurrences will be represented through immutable Events.

An Event describes something that has already occurred.

Events do not represent commands, intentions or routing instructions.

Examples include:

- project.created;
- task.completed;
- run.failed;
- artifact.approved;
- decision.committed;
- experiment.completed;
- metric.threshold_exceeded.

Events may reference their direct cause and may share correlation
identifiers with related Events, Runs and workflows.

Routing and reaction logic will remain separate from Event data.

## Rationale

This separation enables:

- event-driven workflows;
- lazy agent activation;
- asynchronous execution;
- auditability;
- temporal reconstruction;
- external integrations;
- idempotent processing;
- reduced agent coupling;
- scalable orchestration.

## Immutability

Events represent historical facts and should not be silently rewritten.

If later information changes the interpretation or state of an entity,
a new Event should be emitted rather than modifying the original Event.

## Security

Event payloads should contain only the information required for the
occurrence to be understood and processed.

Sensitive or large resources should preferably be referenced rather
than embedded directly.

Possession of an Event does not imply authorization to access all
resources referenced by it.

## Consequences

The organization will require future Event routing and Event processing
components.

Event types must be versionable.

Consumers should be designed to tolerate duplicate delivery and use
idempotency where necessary.