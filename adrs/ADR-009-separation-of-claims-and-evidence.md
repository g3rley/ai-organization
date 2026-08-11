# ADR-009 — Separation of Claims, Evidence and Sources

Status: Accepted
Date: 2026-08-11

## Context

Language models and multi-agent systems can easily transform repeated
assertions into apparent organizational knowledge without preserving
the evidence supporting those assertions.

Multiple agents may also reproduce information derived from the same
underlying source, creating false impressions of independent confirmation.

The organization requires explicit epistemic structure.

## Decision

Claims, Evidence and Sources will be treated as distinct concepts.

A Claim represents a proposition asserted within the organization.

Evidence represents a specific observation, measurement, finding or
information item that may support, contradict or contextualize Claims.

A Source identifies the provenance from which Evidence was obtained.

Model-generated statements do not automatically constitute Evidence.

Claims may exist without Evidence, but their epistemic status must remain
appropriate to the available support.

Evidence may support or contradict multiple Claims.

## Evidence Quality

Evidence assessment should consider dimensions including:

- source reliability;
- relevance;
- directness;
- independence;
- methodological strength;
- recency.

Evidence quantity alone must not determine epistemic confidence.

## Provenance

Evidence should preserve sufficient provenance to identify common-source
dependencies and avoid treating repeated derivatives of one source as
independent confirmation.

## Organizational Knowledge

Repeated assertion does not make a Claim true.

Confidence does not substitute for Evidence.

Human assertions are subject to the same epistemic distinction between
Claim and Evidence as agent-generated assertions.

## Consequences

The organization requires mechanisms for:

- Claim extraction;
- Evidence capture;
- provenance tracking;
- Evidence verification;
- contradictory Evidence detection;
- Evidence quality assessment;
- epistemic status updates.

These mechanisms will form the basis of the future Evidence Engine.