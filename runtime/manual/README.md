# Manual Organization Runtime

Version: 0.1.0

## Purpose

The Manual Organization Runtime provides the first executable operating
environment for the AI Organization.

It allows real Projects and Workflows to be executed before implementation
of an automated Orchestrator, Context Compiler, Policy Engine, database,
event bus or Organization MCP server.

During this phase:

- organizational state remains external to language models;
- humans supervise persistence and state transitions;
- language models execute bounded Runs;
- canonical schemas define organizational records;
- Git provides temporary versioned persistence for non-sensitive prototype state.

The Manual Runtime is intentionally temporary.

Its primary purpose is to test organizational semantics before automation.


## Core Rule

A model conversation is not organizational state.

ChatGPT, Claude or any other model may reason about a Run, but canonical
organizational state exists only after valid records are persisted by the
runtime operator.


## Responsibilities

The Manual Runtime operator temporarily performs functions that will later
belong to automated components.

The operator is responsible for:

1. reading the current Workflow state;
2. materializing the next Task;
3. resolving required capabilities against the Agent Registry;
4. selecting the Agent Definition;
5. selecting an execution model;
6. compiling the relevant execution context;
7. creating the Run record;
8. executing the Run using a model;
9. collecting the proposed outputs;
10. validating canonical records;
11. performing required Evaluations;
12. recording Events and state transitions;
13. applying human approvals when required.


## Canonical State

Manual Project instances are stored under:

    runtime/instances/<project_id>/

The repository is being used as a temporary external state store.

This satisfies the architectural requirement that organizational state
remain outside model-native conversation history.

A production implementation is expected to replace this state layer with
a database and dedicated Artifact storage.


## Project Instance Layout

Each manual Project instance should use:

    runtime/instances/<project_id>/
    ├── project.yaml
    │
    ├── tasks/
    │   └── <task_id>.yaml
    │
    ├── runs/
    │   └── <run_id>/
    │       ├── run.yaml
    │       ├── context-manifest.yaml
    │       └── response.md
    │
    ├── artifacts/
    │   └── <artifact_id>.yaml
    │
    ├── claims/
    │   └── <claim_id>.yaml
    │
    ├── evidence/
    │   └── <evidence_id>.yaml
    │
    ├── evaluations/
    │   └── <evaluation_id>.yaml
    │
    ├── decisions/
    │   └── <decision_id>.yaml
    │
    ├── events/
    │   └── <event_id>.yaml
    │
    └── memory/
        └── <memory_id>.yaml


## Canonical versus Supporting Files

The following files represent canonical organizational records:

- project.yaml;
- Task YAML files;
- Run YAML files;
- Artifact YAML files;
- Claim YAML files;
- Evidence YAML files;
- Evaluation YAML files;
- Decision YAML files;
- Event YAML files;
- Memory YAML files.

Files such as:

    context-manifest.yaml
    response.md

are execution-support records.

They are not independent canonical organizational entities.


## Run Lifecycle

A Manual Run follows this lifecycle:

    Task ready
        ↓
    Agent selected
        ↓
    Run created
        ↓
    Context compiled
        ↓
    Model execution
        ↓
    Proposed outputs returned
        ↓
    Structural validation
        ↓
    Referential validation
        ↓
    Policy checks
        ↓
    Evaluation when required
        ↓
    Canonical outputs persisted
        ↓
    Run terminated
        ↓
    Task completion evaluated
        ↓
    Event emitted
        ↓
    Workflow progresses


## Step 1 — Determine Current Workflow State

Read:

    project.yaml

and identify:

    workflow.definition_id
    workflow.definition_version
    workflow.current_state

Then load the corresponding Workflow Definition.

Do not infer the next organizational action from conversation history.


## Step 2 — Materialize the Next Task

Use the current Workflow Step and create a canonical Task.

The Task must preserve:

- purpose;
- required capabilities;
- inputs;
- expected outputs;
- completion criteria;
- authority;
- resource limits;
- dependencies.

The Workflow Step itself is not the Task.

It is the reusable process definition from which the Task is materialized.


## Step 3 — Resolve Agent Capability

Read:

    agents/registry.yaml

Find active Agent Definitions possessing all required capabilities.

Then check:

- Agent authority;
- Project constraints;
- Task authority;
- applicable Policies.

The Agent name alone must not determine routing.


## Step 4 — Select Execution Model

Model selection is temporary and manual during Runtime v0.1.

The operator should consider:

- Agent runtime requirements;
- Task complexity;
- tool requirements;
- desired evaluator independence;
- cost;
- latency.

The selected provider is recorded in the Run.

Agent Definitions remain model-independent.


## Step 5 — Create the Run

Create the canonical Run record before execution.

At minimum record:

- Run ID;
- Task ID;
- attempt number;
- selected Agent Definition;
- selected execution type;
- runtime versions;
- context references;
- start timestamp.

Run status becomes:

    running


## Step 6 — Compile Context

Create:

    runs/<run_id>/context-manifest.yaml

The context manifest records what was supplied to the model.

It should reference rather than duplicate canonical state whenever possible.

Example:

    schema_version: "0.1.0"

    run_id: run_example_001

    agent:
      id: agent_market_intelligence
      version: "0.1.0"

    task:
      id: task_market_research_001

    project:
      id: proj_example_001

    policies:
      - policy_security_baseline
      - policy_evidence_baseline
      - policy_cost_control_baseline

    artifacts:
      - art_product_thesis_001_r1

    claims: []

    evidence: []

    memory: []

    evaluation_definitions: []

    prompt_wrapper:
      ref: prompts/manual-run-wrapper.md
      version: "0.1.0"

The actual context sent to the model may contain the relevant content of
these records.

The manifest exists to preserve reproducibility and auditability.


## Step 7 — Execute One Bounded Run

Use the universal Manual Run Wrapper.

A Run should have one bounded organizational purpose.

Do not use a model conversation as an indefinite autonomous employee.

When a materially different Task begins, create another Run.


## Step 8 — Treat Model Output as Proposed State

A language model response is not automatically canonical.

The response may propose:

- Artifacts;
- Claims;
- Evidence;
- Decision proposals;
- Task proposals;
- Events;
- escalations.

Before persistence, the operator must check that proposed records conform
to organizational contracts.


## Step 9 — Validate

Validation should occur in this order:

    1. canonical entity schema
    2. Artifact Type schema where applicable
    3. identifier and reference integrity
    4. Policy requirements
    5. Evaluation requirements

Structural validity does not imply factual correctness.


## Step 10 — Persist Canonical Outputs

Only validated records should be persisted into the appropriate Project
instance directories.

Model prose that is not represented through a canonical organizational
record should not silently become Project state.


## Step 11 — Complete the Run

Update the Run with:

- outputs;
- resource usage when known;
- Evaluation references;
- termination reason;
- end timestamp.

Terminal Run records should not be silently rewritten after completion.


## Step 12 — Evaluate Task Completion

A successful Run does not automatically complete a Task.

Check the Task completion criteria.

For example:

    Artifact produced
        +
    Artifact schema valid
        +
    Evaluation passed
        ↓
    Task completed

If criteria are not met, the Task remains incomplete or enters review,
retry or escalation.


## Step 13 — Emit Event

State changes should produce canonical Events.

Examples:

    task.completed
    artifact.created
    evaluation.completed
    decision.committed
    discovery.market_research_accepted

Events describe facts that already occurred.

They do not contain routing instructions.


## Step 14 — Advance Workflow

Evaluate the current Workflow transition conditions.

If one transition becomes valid:

- update Project workflow.current_state;
- record the relevant Event;
- materialize the next Task when required.

Do not advance the Workflow merely because a model recommended doing so.


## Human Approval

Human approval must remain explicit.

When a Workflow or Policy requires human approval:

    Model recommendation
            ↓
    Decision proposal
            ↓
    Human review
            ↓
    explicit approval
            ↓
    committed Decision

Silence does not equal approval.


## Git Discipline

For the manual prototype, significant organizational transitions should
receive Git commits.

Examples:

    state(proj_x): start startup discovery

    run(proj_x): complete initial product thesis

    eval(proj_x): evaluate market report

    decision(proj_x): commit discovery continuation decision

Git history provides temporary organizational auditability.


## Information Security

Never commit:

- API keys;
- passwords;
- OAuth tokens;
- private keys;
- credentials;
- authentication cookies.

During the manual prototype, do not use identifiable patient or sensitive
clinical data.

Use public, synthetic or appropriately de-identified information until a
dedicated secure data architecture and access-control layer exists.

Private repository access does not convert a repository into a secret manager.


## Success Criterion for Manual Runtime v0.1

The Manual Runtime is successful when one real Project can execute:

    Project
    → Startup Discovery Workflow
    → Tasks
    → Runs
    → Typed Artifacts
    → Claims / Evidence
    → Evaluations
    → Evidence Review
    → Decision Proposal
    → Human Decision
    → terminal Workflow state

without relying on model conversation history as canonical organizational
state.

Only after this integration test should major runtime automation begin.