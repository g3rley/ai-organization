# ADR-019 — Evaluation Definitions as Versioned Rubrics

Status: Accepted
Date: 2026-08-11

## Context

The AI Organization possesses a canonical Evaluation entity but requires
repeatable definitions describing how particular classes of outputs should
be assessed.

Without versioned Evaluation Definitions, different evaluators may apply
inconsistent criteria and historical scores would not be meaningfully
comparable.

## Decision

Reusable Evaluation Definitions will be maintained as versioned
organizational configuration.

An Evaluation Definition specifies:

- target type;
- evaluation kind;
- evaluation method;
- evaluator independence requirements;
- criteria;
- criterion weights;
- deterministic checks;
- semantic rubrics;
- scoring rules;
- verdict thresholds.

Concrete assessment results remain represented through Evaluation entities.

## Mixed Evaluation

Evaluation Definitions may combine deterministic and probabilistic methods.

Deterministic checks should be preferred for properties that can be
reliably verified by code.

Examples include:

- schema validity;
- referential integrity;
- required-field presence;
- coverage checks;
- numeric thresholds.

Model-based evaluation should be reserved for criteria requiring semantic
judgment.

Examples include:

- strategic coherence;
- analytical completeness;
- uncertainty calibration;
- quality of alternatives;
- reasoning about contradictory Evidence.

## Blocking Criteria

Some criteria may be classified as blocking.

Failure of a blocking criterion may cause the overall Evaluation to fail
regardless of aggregate score.

Structural validity and material referential integrity are examples of
potential blocking criteria.

## Evaluation Context

A model-based evaluator should receive sufficient canonical context to
evaluate the target rather than judging prose quality alone.

Relevant context may include:

- Claims;
- Evidence;
- provenance;
- Decisions;
- Policies;
- supporting Artifacts.

## Independence

Evaluator independence should be proportional to materiality and risk.

Self-assessment may be useful for preliminary quality control but should
not substitute for independent review of materially consequential work.

## Versioning

Evaluation Definition versions must be preserved with concrete Evaluation
records.

Scores produced under materially different rubrics must not be treated as
directly equivalent without appropriate normalization or analysis.

## Consequences

The organization now has reusable quality standards for its initial typed
Artifacts.

These Definitions can later support:

- Task completion gates;
- Artifact review;
- model comparison;
- Agent performance analysis;
- Workflow optimization;
- continuous organizational learning.