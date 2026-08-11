# ADR-020 — First Manual Startup Discovery Workflow

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization now possesses:

- canonical domain entities;
- governance Policies;
- Agent Contracts;
- typed Artifact interfaces;
- Evaluation Definitions;
- a reusable Workflow Contract.

The organization therefore has sufficient structure to instantiate its first
complete cross-agent process.

However, the current operational Agent nucleus does not yet include Customer
Research, Experimentation, Financial Analysis or Engineering Agents.

Treating market analysis alone as full startup validation would therefore
overstate what the organization has actually learned.

## Decision

The first operational Workflow will be:

Startup Discovery — Opportunity Screening v0.1.

Its purpose is to determine whether a startup thesis has sufficient strategic
coherence and external Evidence to justify proceeding to a dedicated
Customer Discovery stage.

The Workflow does not authorize implementation and does not represent full
startup validation.

## Process

The Workflow coordinates:

Product Thesis
→ Product Thesis Evaluation
→ Market Research
→ Market Report Evaluation
→ Independent Evidence Review
→ Evidence Review Evaluation
→ updated Product Thesis
→ explicit Go/No-Go Decision proposal
→ human approval
→ committed Decision.

## Positive Outcome

The positive terminal state is:

`ready_for_customer_discovery`

This means the opportunity is sufficiently structured to justify additional
discovery investment.

It does not mean:

- customer demand is validated;
- willingness-to-pay is validated;
- product-market fit exists;
- implementation should begin;
- production deployment is authorized.

## Insufficient Evidence

`insufficient_evidence` is a valid successful Workflow termination.

The organization should prefer an explicit conclusion of insufficient
Evidence over fabricated confidence or premature continuation.

## Stop Outcome

`stopped` is also considered successful Workflow execution.

Workflow success measures process completion, not whether the underlying
business thesis received a positive recommendation.

This distinction reduces incentives for Agents to favor continuation.

## Human Authority

The final discovery continuation Decision requires explicit human approval.

The initial Workflow may produce recommendations and Decision proposals but
must not autonomously commit the Go/No-Go choice.

## Orchestrator

The Orchestrator is not invoked at every Workflow state.

Deterministic Workflow coordination should handle normal progression.

The Orchestrator is reserved for situations requiring replanning,
capability resolution or escalation.

## Evaluations

Typed Artifacts are subject to their canonical Evaluation Definitions before
material downstream progression.

Revision loops are allowed but remain bounded by Run, retry, cost and Workflow
limits.

## Runtime

The initial Workflow is intentionally executable manually.

ChatGPT, Claude and humans may act as temporary runtime components while
organizational state is maintained externally through the canonical
Artifacts and repository conventions.

No MCP server or automated Orchestrator is required for the first execution.

## Consequences

The AI Organization can now execute its first end-to-end organizational
process without relying on unrestricted multi-agent conversation.

The next major milestone is a Manual Organization Runtime capable of
instantiating this Workflow against a real Project.