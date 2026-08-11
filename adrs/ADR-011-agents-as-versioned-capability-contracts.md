# ADR-011 — Agents as Versioned Capability Contracts

Status: Accepted
Date: 2026-08-11

## Context

A common multi-agent design pattern treats agents as personas coupled
directly to prompts or specific language models.

This creates weak authority boundaries, provider coupling, uncontrolled
communication and poor evaluation.

The AI Organization requires reusable autonomous reasoning roles that can
operate across different models and runtime environments.

## Decision

Agents will be represented through versioned Agent Definitions.

An Agent Definition specifies:

- mission;
- responsibilities;
- explicit exclusions;
- capabilities;
- accepted inputs;
- expected outputs;
- tool permissions;
- memory permissions;
- authority;
- interaction permissions;
- activation rules;
- completion conditions;
- escalation rules;
- runtime requirements;
- resource constraints;
- evaluation criteria.

An Agent Definition is not a running process and is not bound to a specific
language model.

Model selection is a runtime responsibility.

## Communication

Free-form continuous communication between agents will not be the default
coordination mechanism.

Agent interaction should occur through explicit organizational structures
such as:

- Tasks;
- Artifacts;
- Reviews;
- Decisions;
- Events;
- Escalations.

## Authority

Agent authority is bounded by higher-level organizational constraints.

Effective authority is the intersection of:

- organizational Policies;
- Project autonomy;
- Agent Definition;
- Task authority;
- Tool permissions.

An Agent Definition cannot grant authority prohibited at a higher level.

## Memory

Direct persistent Memory writes should not be available to most Agents.

Agents should generally produce Artifacts, Claims and Evidence from which
Memory may later be deliberately consolidated.

## Self-Modification

Agents may propose improvements but must not silently modify their own
definitions, permissions or evaluation criteria.

## Agent Creation

Agents must not create unrestricted new Agents by default.

Specialist or ephemeral Agent activation must remain subject to
Orchestrator and Policy controls.

## Model Independence

Agent Definitions describe runtime requirements rather than specific model
providers whenever practical.

This permits model routing based on capability, cost, latency and historical
performance.

## Consequences

The organization requires:

- an Agent Registry;
- capability-based Task routing;
- runtime model routing;
- authority enforcement;
- context compilation;
- agent evaluation;
- Agent Definition versioning.