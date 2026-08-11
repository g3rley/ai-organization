# Agent System

Version: 0.1.0

## Principle

An Agent is a versioned autonomous reasoning capability contract.

An Agent is not:

- a job title;
- a model provider;
- a permanent process;
- a conversation thread;
- a prompt;
- a tool.

## Registry

`registry.yaml` identifies:

- available Agent Definitions;
- organizational capabilities;
- Agent classes;
- Agent Contract locations.

The Registry is used for capability-based routing.

## Agent Classes

### Core

Reusable roles fundamental to organizational operation.

Core does not mean continuously running.

### Specialist

Reusable expertise activated only when relevant Tasks or Workflow
states require the capability.

### Ephemeral

Narrowly scoped Agent Definitions created or instantiated for a
specific bounded purpose.

Ephemeral Agents must remain subject to normal Policy and authority
controls.

## Routing

Tasks should request capabilities rather than specific job titles
whenever practical.

Example:

    required_capabilities:
      - market.research
      - competitor.analysis

The future Agent Router may consider:

- capability match;
- authority;
- Agent status;
- historical Evaluation performance;
- cost;
- latency;
- Project constraints;
- Task risk.

## Model Independence

Agent Definitions must not normally bind directly to GPT, Claude or
another model provider.

Model selection is a runtime concern.

## Activation

Registered Agents are inactive by default.

An Agent should be invoked only because of:

- a Task;
- a Workflow Step;
- a Review request;
- an Event;
- an Escalation;
- an explicit human request.

Ambient autonomous activity is prohibited by default.

## Specialization

New Agents should be created only when specialization has demonstrated
sufficient value to justify additional coordination complexity.

A role should remain a capability, skill, tool or deterministic Workflow
when a separate autonomous reasoning boundary is unnecessary.