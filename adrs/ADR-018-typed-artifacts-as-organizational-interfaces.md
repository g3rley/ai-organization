# ADR-018 — Typed Artifacts as Organizational Interfaces

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization now contains operational Agent Definitions that produce
Artifacts such as Product Theses, Market Reports and Evidence Reviews.

Artifact type names alone do not guarantee interoperable outputs.

Without structured contracts, downstream Agents and Workflows would need
to interpret arbitrary prose, recreating conversational coupling between
organizational components.

## Decision

Material reusable Artifact types will have explicit versioned content schemas.

An Artifact remains represented through the canonical Artifact envelope.

The Artifact Type Registry maps semantic Artifact types to their corresponding
content schemas and routing metadata.

The initial typed Artifacts are:

- strategy.product_thesis;
- research.market_report;
- review.evidence.

## Artifact Envelope and Content Schema

The canonical Artifact schema defines common properties such as:

- identity;
- Project ownership;
- revision;
- status;
- provenance;
- links;
- content location.

Artifact Type schemas define the structure of `Artifact.content.body`.

These are separate responsibilities.

## Structured Handoffs

Agents may use unstructured reasoning internally, but material organizational
handoffs should preferentially use structured Artifacts.

This reduces interpretation ambiguity and permits deterministic validation.

## Claims and Evidence

Artifact schemas should reference canonical Claims and Evidence rather than
silently duplicating them as independent sources of truth.

Artifacts may summarize and contextualize Claims and Evidence, but epistemic
state remains governed by the canonical entities.

## Validation

Artifact acceptance may include:

1. Artifact envelope validation;
2. Artifact Type resolution;
3. content schema validation;
4. referential integrity checks;
5. Policy evaluation;
6. Evaluation or Review where required.

Passing structural validation does not imply epistemic correctness.

## Versioning

Artifact revision and Artifact Type schema version are distinct concepts.

Artifact revision tracks the evolution of a specific logical Artifact.

Artifact Type schema version tracks evolution of the organizational interface.

## Governance

Artifact Type Registry metadata may provide routing recommendations.

Review or approval requirements remain governed by Policies, Tasks and
Workflows rather than the Registry alone.

## Consequences

Agents can now exchange structured organizational outputs without relying
on free-form conversations.

Workflows and Evaluation Definitions may target explicit Artifact types and
validate their structure deterministically.