# ADR-017 — Initial Operational Agent Nucleus

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization now possesses an Agent Registry containing an
initial portfolio of reusable Agent Definitions.

Implementing every registered Agent immediately would create unnecessary
upfront complexity before the organizational runtime has been tested.

A smaller operational nucleus is sufficient to exercise the most important
organizational primitives.

## Decision

The first operational Agent Contracts will be:

1. Orchestrator
2. Product Strategist
3. Evidence Reviewer
4. Market Intelligence

These Agents provide sufficient capability to test an initial loop:

Human Objective
→ Task decomposition
→ strategic analysis
→ market research
→ Evidence review
→ Decision proposal

## Orchestrator

The Orchestrator coordinates work but should not become a universal
specialist.

Specialized analysis should be routed to Agents possessing the relevant
capabilities.

## Product Strategist

The Product Strategist converts opportunity information into explicit
strategic theses, assumptions, alternatives and Decision support.

It does not commit strategic Decisions.

## Market Intelligence

Market Intelligence performs external market and competitor research.

It must distinguish sourced observations from estimates, assumptions
and inference.

## Evidence Reviewer

The Evidence Reviewer provides an independent epistemic control layer.

Its purpose is not primarily idea generation but verification of Claims,
Evidence quality, provenance, contradictions and uncertainty.

## Model Independence

None of the initial Agent Definitions are bound to a specific model
provider.

Runtime model selection remains separate from organizational role.

## Tool Abstraction

Agent Contracts request abstract tool capabilities rather than specific
MCP servers, connectors or vendors.

Tool capability resolution will be designed separately.

## Consequences

The organization can now begin designing its first executable Workflow
against real Agent Definitions.

Remaining registered Agents should be implemented incrementally as
Workflow needs demonstrate their value.