# ADR-003 — Project as a Bounded Organizational Initiative

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization requires a canonical object representing an
initiative independently of conversations, models and workflows.

## Decision

A Project will represent a bounded organizational initiative.

The Project will define:

- identity;
- ownership;
- primary objective;
- scope;
- constraints;
- initial hypotheses;
- risk;
- delegated autonomy;
- workflow association.

Tasks, runs, artifacts, evidence, decisions, events and memory will
remain separate canonical entities associated with the Project.

## Rationale

Separating project identity from execution state prevents the Project
object from becoming an unstructured container for all organizational
information.

It also permits different workflows and agent configurations to operate
on the same Project over time.

## Consequences

The Project remains relatively small and stable.

Execution history must be reconstructed through related entities rather
than embedded directly in the Project.