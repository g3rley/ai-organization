# ADR-010 — Deliberate Organizational Memory

Status: Accepted
Date: 2026-08-11

## Context

Agentic systems frequently treat conversation history, retrieved documents
and vector database contents as interchangeable forms of memory.

This creates stale knowledge, duplication, weak provenance, inconsistent
state and uncontrolled information retention.

The AI Organization requires memory that remains distinguishable from
canonical organizational entities.

## Decision

Persistent organizational Memory will be explicitly curated.

A Memory Record represents contextual knowledge deliberately retained for
future reasoning or execution.

Canonical entities such as Decisions, Evidence, Artifacts, Events, Tasks,
Runs, Policies and Workflows will remain authoritative in their respective
domains and will not be replaced by Memory representations.

Working context used during a Run will not automatically become persistent
Memory.

## Memory Types

The initial memory model supports:

- episodic;
- semantic;
- project context;
- organizational context.

## Provenance

Persistent Memory must preserve references to the organizational entities
or external resources from which it was derived.

Memory without sufficient provenance should not silently become trusted
organizational knowledge.

## Lifecycle

Memory may be:

- active;
- under review;
- superseded;
- expired;
- retracted;
- archived.

Memory must support invalidation when its underlying sources, Evidence or
Decisions become obsolete or invalid.

## Retention

Persistent Memory requires an explicit retention purpose.

Information must not be retained indefinitely merely because it appeared
in a conversation or Run.

## Access

Memory retrieval must respect project boundaries, sensitivity,
actor permissions and purpose limitations.

Possession of semantic relevance does not imply authorization.

## Retrieval

Memory retrieval should consider more than semantic similarity.

Future retrieval mechanisms may combine:

- metadata filtering;
- structured relationships;
- semantic search;
- temporal validity;
- epistemic quality;
- permissions;
- task relevance.

## Organizational Learning

Memory does not directly modify Policies, Workflows, Agent Definitions
or governance.

Potential organizational improvements must pass through the controlled
Lesson and organizational learning process.

## Consequences

The organization will require future mechanisms for:

- memory candidate generation;
- memory consolidation;
- deduplication;
- provenance verification;
- invalidation;
- expiration;
- permission-aware retrieval;
- context compilation.

A vector database is an implementation option, not the definition of
organizational Memory.