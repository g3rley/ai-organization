# ADR-013 — Minimum Governance Baseline

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization now possesses canonical definitions for Projects,
Artifacts, Decisions, Tasks, Runs, Events, Claims, Evidence, Memory,
Agents and Policies.

Before defining operational Workflows or activating autonomous Agents,
the organization requires a minimum set of enforceable governance rules.

## Decision

The initial governance baseline will contain five Organization-level
Policy domains:

1. Authority
2. Security
3. Evidence
4. Cost Control
5. Escalation

The initial Policy set will intentionally favor bounded autonomy and
human approval for materially consequential external actions.

Autonomy may increase later when evaluation data demonstrates sufficient
reliability.

## Authority

External financial commitments, contractual obligations, official
external communications, production changes and governance changes
require explicit human approval in the initial maturity stage.

## Security

Credential exposure, unauthorized authority changes originating from
untrusted content and uncontrolled transmission of restricted information
are prohibited.

Critical security controls must fail closed.

## Evidence

Material Claims and Decisions require proportionate Evidence.

Repeated model assertions do not constitute independent Evidence.

Contradictory material Evidence must remain visible and may require review.

## Cost

Agent activity is treated as an organizational resource.

Retries, parallel execution, premium model use and independent reviews
must be proportional to expected organizational value.

## Escalation

Agents and workflows must stop autonomous execution when authority,
risk, expertise or Policy resolution becomes materially insufficient.

Escalation is a successful organizational control mechanism and must
not be treated automatically as agent failure.

## Maturity

These Policies represent a conservative v0.1 baseline.

They are expected to evolve through:

Execution
→ Evaluation
→ Evidence
→ Lesson
→ Governance Change

rather than through informal or silent modification.

## Consequences

The organization can now reason explicitly about whether a proposed
action should be:

- allowed;
- proposed only;
- executed after approval;
- denied;
- reviewed;
- escalated.

Operational Workflows may now be designed against a defined governance
boundary.