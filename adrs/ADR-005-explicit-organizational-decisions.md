# ADR-005 — Explicit Organizational Decisions

Status: Accepted
Date: 2026-08-11

## Context

Multi-agent systems frequently blur the distinction between recommendations,
conversational consensus and organizational decisions.

This creates ambiguity about authority, execution and accountability.

## Decision

Material organizational choices will be represented through explicit
Decision entities.

Agent recommendations, messages and artifact conclusions are not considered
committed organizational decisions.

A Decision must explicitly identify:

- the decision question;
- considered alternatives;
- relevant evidence and artifacts;
- authority;
- objections;
- selected option when committed;
- rationale;
- impact;
- reversibility;
- review conditions where appropriate.

Committed decisions must not be silently rewritten.

Changed decisions should be superseded by new decisions while preserving
historical traceability.

## Rationale

Explicit decisions enable:

- clear authority;
- auditability;
- structured disagreement;
- evidence-based reasoning;
- human-in-the-loop governance;
- reversibility analysis;
- organizational learning;
- downstream automation.

## Consequences

Agents may propose decisions without having authority to commit them.

Workflows must distinguish proposal, review and commitment.

Downstream execution should depend on committed decisions rather than
informal model outputs whenever the decision is material.