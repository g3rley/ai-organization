# ADR-004 — Artifact-Centric Organizational Operation

Status: Accepted
Date: 2026-08-11

## Context

Multi-agent systems can easily become dependent on transient
conversation histories and unstructured exchanges between agents.

This makes work difficult to version, review, audit, reuse and evaluate.

## Decision

Material organizational work will be represented through canonical
Artifacts.

An Artifact is a persistent, identifiable and versioned organizational
work product.

Artifacts may contain content directly or reference content stored in
external systems.

Agent conversations are coordination mechanisms and are not considered
the canonical organizational record.

Reviews, analyses, plans and specifications may themselves be represented
as Artifacts.

## Rationale

Artifact-centric operation enables:

- versioning;
- provenance;
- independent review;
- multi-agent collaboration;
- model-provider independence;
- auditability;
- structured handoffs;
- evaluation;
- organizational memory.

## Consequences

Agents must produce explicitly defined outputs rather than merely
conversational responses.

Artifact storage and artifact metadata may be implemented separately.

Multiple revisions of an Artifact may coexist.

Rejected and superseded revisions should remain traceable.