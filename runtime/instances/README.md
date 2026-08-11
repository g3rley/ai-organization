# Manual Project Instances

This directory contains temporary Git-backed organizational state used by
the Manual Organization Runtime.

Each Project receives its own directory:

    runtime/instances/<project_id>/

## Purpose

This directory is an implementation mechanism for the manual prototype.

It is not part of the permanent organizational architecture.

The long-term architecture is expected to move operational state into a
dedicated database and Artifact storage layer.


## Naming

Canonical entity files should use their canonical IDs whenever practical.

Examples:

    tasks/task_market_research_001.yaml

    claims/claim_customer_problem_001.yaml

    evidence/evd_interview_001.yaml

    evaluations/eval_market_report_001.yaml

    decisions/dec_discovery_gate_001.yaml

    events/evt_market_research_completed_001.yaml


## Runs

Runs use directories because execution may have supporting records:

    runs/run_market_research_001/
    ├── run.yaml
    ├── context-manifest.yaml
    └── response.md

Only `run.yaml` is the canonical Run entity.


## Artifact Revisions

Do not overwrite previous Artifact content revisions.

Create new revision-specific records.

Example:

    art_market_report_001_r1.yaml
    art_market_report_001_r2.yaml

Both may share the same logical Artifact ID.


## Events

Events are immutable.

Never edit an Event to represent a later interpretation.

Record another Event.


## Completed Runs

A completed, failed, cancelled or timed-out Run should be treated as a
historical execution record.

Corrections require a new Run.


## Sensitive Data

This manual state layer must not contain secrets or identifiable clinical,
patient or other restricted personal information.