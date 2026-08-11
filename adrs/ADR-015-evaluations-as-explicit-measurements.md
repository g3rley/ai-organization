# ADR-015 — Evaluations as Explicit Organizational Measurements

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization requires objective mechanisms for determining whether
Runs, Artifacts, Agents, Workflows and Decisions meet expected quality,
performance, safety and outcome requirements.

Without explicit Evaluation records, model outputs may be accepted merely
because execution completed successfully.

The organization also requires comparable historical performance data for
continuous improvement and model routing.

## Decision

Concrete assessments will be represented through canonical Evaluation
entities.

Reusable Evaluation Definitions will describe how a class of targets should
be assessed.

Evaluation entities will record the result of specific assessments.

Evaluation Definitions are organizational configuration.

Evaluation records are organizational measurements.

## Evaluation Methods

Evaluations may be:

- deterministic;
- model-based;
- human;
- outcome-based;
- mixed.

Deterministic evaluation should be preferred when the relevant criterion
can be reliably measured without probabilistic reasoning.

## Independence

Self-assessment may be used as an inexpensive preliminary control but must
not automatically be treated as independent verification.

The required degree of evaluator independence should increase with risk,
impact and uncertainty.

## Authority

An Evaluation measures a target.

It does not automatically approve an Artifact, commit a Decision, complete
a Task or modify governance.

Policies and Workflows determine the organizational consequences of
Evaluation results.

## Execution

When an Evaluation itself requires model or agent execution, that execution
should be represented through a Run.

The Evaluation should reference the Run rather than duplicating model,
token, cost and tool-call telemetry.

## Outcome Evaluation

Where practical, organizational performance should eventually be evaluated
against real-world outcomes rather than only model-based assessments.

A high model-judge score does not guarantee real-world success.

## Continuous Improvement

Evaluation history may be used to compare:

- Agent Definition versions;
- Workflow versions;
- model routing strategies;
- prompts;
- tools;
- execution approaches.

Evaluation results may generate Lesson candidates but must not silently
modify organizational definitions or governance.

## Consequences

The organization can now measure quality independently from execution
completion.

Future systems can use Evaluation history for:

- retries;
- Task acceptance;
- Agent performance management;
- Workflow optimization;
- model routing;
- cost-quality optimization;
- organizational learning.