# AI Organization Design Principles

Version: 0.1.0

## P01 — Organization before agents

Design the organization before creating specialized agents.

## P02 — Agent ≠ role ≠ skill ≠ tool ≠ workflow

Use an agent only when autonomous reasoning provides material value.

## P03 — State outside the model

Persistent organizational state must remain external to LLM context.

## P04 — Artifacts over conversations

Important work should produce structured artifacts.

## P05 — Context is compiled, not accumulated

Provide each agent the minimum relevant context required for its task.

## P06 — Lazy agents

Agents should be activated by work or events, not remain permanently active.

## P07 — Evidence proportional to impact

Higher-impact decisions require stronger evidence.

## P08 — Independence proportional to risk

Critical proposals should receive independent review.

## P09 — Determinism first

Do not use probabilistic reasoning where deterministic execution is superior.

## P10 — Explicit authority

Agents should know what they may decide, execute, recommend and escalate.

## P11 — Structured disagreement

Disagreement must produce objections, counterproposals or evidence requests,
not endless debate.

## P12 — Stop conditions everywhere

Every agentic process must have completion, timeout and escalation conditions.

## P13 — Memory is curated

Retrieval is not memory and conversation history is not organizational truth.

## P14 — Learning is versioned

Organizational learning must generate auditable changes.

## P15 — Models are replaceable

Organizational architecture must not depend on one model provider.

## P16 — MCP exposes capabilities, not governance

Tool connectivity must remain separate from organizational decision authority.

## P17 — Minimize coordination tax

Adding another agent must provide more expected value than coordination cost.

## P18 — Human attention is expensive

Escalate to humans only where human judgment has meaningful marginal value.

## P19 — Autonomy is earned

Expand autonomy only after evaluation demonstrates sufficient reliability.

## P20 — Complexity must justify itself

Do not implement infrastructure whose value has not yet been demonstrated.