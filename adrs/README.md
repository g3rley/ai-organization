# ADRs

Este diretório registra as decisões arquiteturais importantes da organização.

O objetivo dos ADRs é documentar o porquê de uma escolha de arquitetura, não apenas o que foi implementado. Isso cria histórico de contexto, trade-offs, restrições e decisões futuras.

## Convenção de nomenclatura

- `ADR-001-<tema>.md`
- `ADR-002-<tema>.md`
- `ADR-003-<tema>.md`

## Estrutura esperada

Cada ADR deve conter:

- título;
- contexto;
- problema ou necessidade;
- opções consideradas;
- decisão adotada;
- consequencias esperadas;
- trade-offs;
- status.

## Exemplos esperados

- `ADR-001-separate-intelligence-from-state.md`
- `ADR-002-artifact-centric-operation.md`
- `ADR-003-event-driven-agent-activation.md`

## Uso

Use ADRs quando:

- houver uma decisão de arquitetura que impacte múltiplos fluxos;
- a escolha envolva trade-offs significativos;
- a organização precisar manter contexto para futuras mudanças ou justificativas.
