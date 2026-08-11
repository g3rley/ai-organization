# AI Organization Core Domain Model

Version: 0.1.0
Status: Draft

This document defines the canonical conceptual entities used by the
AI Organization.

Machine-readable schemas must conform to the semantics defined here.

---

# 1. Organization

The top-level governance boundary.

An Organization defines:

- identity;
- authority;
- constitution;
- policies;
- agent definitions;
- workflow definitions;
- shared resources;
- organizational memory.

An Organization may contain multiple Projects.

An Organization is not an agent.

---

# 2. Project

A bounded initiative created to accomplish one or more objectives.

Examples:

- validate a startup idea;
- build a product;
- conduct market research;
- operate an existing business process;
- investigate an incident.

A Project contains its own:

- objectives;
- state;
- tasks;
- artifacts;
- decisions;
- evidence;
- events;
- project memory.

A Project must not depend on conversation history as its canonical state.

---

# 3. Objective

A desired outcome.

An Objective describes what should become true, rather than how it
should be accomplished.

Examples:

Bad:
"Ask the Market Agent to research competitors."

Good:
"Determine whether the Brazilian market contains at least three
commercially viable competitor segments for the proposed product."

Objectives may contain:

- success criteria;
- constraints;
- priority;
- deadline;
- owner;
- parent objective;
- status.

Objectives may decompose into sub-objectives.

---

# 4. Task

A bounded unit of work created to advance an Objective.

A Task must define:

- purpose;
- expected output;
- completion criteria;
- authority boundary;
- relevant inputs;
- dependencies;
- status.

A Task is not equivalent to a prompt.

A prompt may be generated to execute a Task.

One Task may have multiple execution attempts.

---

# 5. Run

A Run is one execution attempt of a Task or Workflow.

A Run records what actually happened.

It may include:

- executor;
- model;
- model version;
- input context;
- tools used;
- timestamps;
- token consumption;
- monetary cost;
- outputs;
- errors;
- termination reason.

Task is intent.

Run is execution.

---

# 6. Agent Definition

A reusable specification of an autonomous reasoning role.

An Agent Definition describes:

- mission;
- responsibilities;
- exclusions;
- inputs;
- outputs;
- available tools;
- memory access;
- authority;
- communication permissions;
- completion criteria;
- escalation criteria;
- evaluation criteria.

An Agent Definition is not a running process.

Agents should be instantiated only when required by work.

---

# 7. Artifact

A persistent work product created by a human, agent, workflow or tool.

Examples:

- Product Specification;
- market analysis;
- financial model;
- ADR;
- PRD;
- code change;
- research report;
- experiment design;
- security review.

Artifacts must be independently identifiable.

Where appropriate, artifacts should support:

- versioning;
- authorship;
- provenance;
- review;
- approval;
- supersession.

Artifacts represent organizational work products.

---

# 8. Claim

A proposition asserted by an actor or artifact.

Examples:

"The target market exceeds BRL 500 million."

"Users prefer asynchronous communication."

"This architecture can support 10,000 requests per second."

Claims should be classifiable as:

- fact;
- inference;
- hypothesis;
- assumption;
- opinion;
- unknown.

Claims may reference Evidence.

Separating Claims from Evidence allows the organization to reason
about what it believes and why.

---

# 9. Evidence

Information used to support, weaken or contextualize a Claim.

Evidence may include:

- external sources;
- internal data;
- experiments;
- analytics;
- interviews;
- measurements;
- observations;
- validated artifacts.

Evidence should preserve provenance whenever possible.

Evidence is not automatically true merely because it exists.

Evidence may have:

- source;
- reliability;
- relevance;
- recency;
- confidence;
- direction.

Direction may be:

- supports;
- contradicts;
- neutral.

---

# 10. Decision

A committed organizational choice between alternatives.

A Decision is not equivalent to:

- an opinion;
- a recommendation;
- an agent response;
- a discussion outcome.

A Decision should record:

- decision question;
- alternatives;
- selected option;
- rationale;
- evidence;
- objections;
- authority;
- approvers;
- timestamp;
- confidence;
- reversibility;
- review conditions.

Once committed, a Decision becomes part of organizational state.

Decisions may later be superseded, but should not be silently rewritten.

---

# 11. Event

An immutable record that something relevant occurred.

Examples:

- project.created;
- task.completed;
- artifact.published;
- decision.committed;
- experiment.finished;
- deployment.failed;
- metric.threshold_exceeded.

Events describe facts about state transitions.

Events may trigger workflows or agents.

Events are not commands.

---

# 12. Memory Record

A persistent piece of contextual knowledge retained for future use.

A Memory Record must have an explicit retention purpose.

Memory may be classified as:

- episodic;
- semantic;
- project;
- organizational.

Memory is not a substitute for canonical entities.

For example:

A committed Decision should remain a Decision.

It should not exist only as a memory embedding.

---

# 13. Workflow Definition

A reusable process definition.

A Workflow defines:

- triggers;
- states;
- steps;
- dependencies;
- actors;
- conditions;
- decision gates;
- outputs;
- failure handling;
- termination conditions.

A Workflow may contain:

- deterministic steps;
- agentic steps;
- human approval steps;
- tool calls.

Workflow Definition describes the process.

Workflow execution is recorded through Runs and Events.

---

# 14. Policy

A machine- or human-enforceable organizational rule.

Examples:

- spending limits;
- human approval thresholds;
- security restrictions;
- evidence requirements;
- escalation rules;
- access-control requirements.

Policies constrain agents and workflows.

Policies take precedence over agent preferences.

---

# 15. Evaluation

A structured assessment of quality or performance.

Evaluations may apply to:

- runs;
- artifacts;
- agents;
- workflows;
- decisions;
- projects.

Evaluations may be:

- deterministic;
- model-based;
- human;
- outcome-based.

Evaluation results should not automatically become policies.

They are inputs to organizational learning.

---

# 16. Lesson

A candidate organizational learning derived from observed outcomes.

Lessons progress through a controlled lifecycle:

candidate
→ under_review
→ validated
→ adopted
→ deprecated

A Lesson may propose changes to:

- policies;
- workflows;
- prompts;
- agent definitions;
- evaluation criteria.

Lessons do not modify governance automatically.

---

# Canonical Relationships

Organization
    has Projects

Organization
    defines Agent Definitions

Organization
    defines Workflow Definitions

Organization
    enforces Policies

Project
    pursues Objectives

Objective
    produces Tasks

Task
    has Runs

Runs
    may produce Artifacts

Artifacts
    may contain Claims

Claims
    may reference Evidence

Evidence
    may support or contradict Claims

Decisions
    reference Claims, Evidence and Artifacts

Decisions
    may create new Tasks

Events
    record important state changes

Events
    may trigger Workflows

Memory Records
    provide contextual knowledge

Evaluations
    measure organizational performance

Lessons
    derive from Evidence, Outcomes and Evaluations