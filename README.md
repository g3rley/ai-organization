# AI Organization

Este repositório define uma arquitetura operacional para governança, agentes, políticas, esquemas e workflows de IA.

## Estrutura

```text
.
├── adrs/
│   └── README.md
├── agents/
│   ├── registry.yaml
│   └── contracts/
├── constitution/
│   ├── constitution.md
│   └── principles.md
├── evals/
├── policies/
│   ├── authority.yaml
│   ├── evidence.yaml
│   ├── escalation.yaml
│   ├── security.yaml
│   └── cost-control.yaml
├── prompts/
├── schemas/
│   ├── project.schema.yaml
│   ├── task.schema.yaml
│   ├── artifact.schema.yaml
│   ├── decision.schema.yaml
│   └── event.schema.yaml
├── workflows/
│   ├── startup-discovery/
│   ├── product-development/
│   └── operations/
├── LICENSE
├── README.md
└──
```

## Visão geral

- `adrs/`: registra decisões arquiteturais e o contexto por trás das escolhas.
- `constitution/`: define regras fundamentais e princípios.
- `agents/`: registra agentes e seus contratos de atuação.
- `policies/`: especifica autoridade, evidência, segurança, escalonamento e custo.
- `schemas/`: valida estruturas de dados de projeto, tarefa, decisão e evento.
- `workflows/`: descreve como operar em descoberta, desenvolvimento e produção.
- `evals/`: local para métricas, revisão de qualidade e avaliação de desempenho.
- `prompts/`: repositório de prompts estruturados e orientados à governança.

## Como usar

1. Defina o projeto usando o esquema de `project.schema.yaml`.
2. Crie tarefas com `task.schema.yaml` e atribua agentes do registro.
3. Valide evidência e decisões usando `evidence.yaml` e `decision.schema.yaml`.
4. Execute os workflows conforme o estágio do ciclo de vida.
5. Mantenha rastreabilidade por eventos, artefatos e aprovação humana.

## Standard operating principles

- autoridade humana sempre preservada;
- evidência antes de conclusão;
- risco e segurança acima de velocidade;
- custo e valor sempre monitorados;
- operação com rastreabilidade total.
