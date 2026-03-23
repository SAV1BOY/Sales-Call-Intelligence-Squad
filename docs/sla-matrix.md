# Matriz de SLAs — Sales Call Intelligence Squad

> Tempos de resposta e entrega para todas as operações do squad.

## SLAs por Tipo de Task

| Tipo | SLA de Entrega | Responsável | Escalation |
|------|---------------|-------------|------------|
| Per-call tasks (intake, audit, scoring, rewrite) | 24h após recebimento da call | Agente owner | sales-chief se > 24h |
| Weekly tasks (review, sync, calibração) | Entrega até sexta-feira 18h | sales-chief | qa-guardian se atrasado |
| Monthly tasks (certificação, patterns) | Entrega até dia 5 do mês seguinte | sales-chief | HRM layer se atrasado |
| Quarterly tasks (intelligence, offer-fit) | Entrega até dia 15 do trimestre seguinte | sales-chief | HRM layer se atrasado |

## SLAs de Quality Gates

| Gate | SLA de Revisão | Responsável |
|------|---------------|-------------|
| Agent-level gate | Imediato (auto-validação) | Agente owner |
| Task-level gate (QA Guardian) | 4h após entrega do agente | qa-guardian |
| Chief-level gate | 8h após aprovação QA | sales-chief |
| Cross-squad gate | 24h antes do envio | sales-chief |

## SLAs de Cross-Squad Handoffs

| Squad Receptor | SLA de Acknowledgment | SLA de Delivery | Escalation |
|---------------|----------------------|-----------------|------------|
| Copy Squad | 72h | 1 semana | sales-chief → copy-chief |
| Traffic Squad | 72h | 1 semana | sales-chief → traffic-chief |
| Brand Squad | 72h | 1 semana | sales-chief → brand-chief |
| Storytelling Squad | 72h | 1 semana | sales-chief → storytelling-chief |
| C-Level Squad | 24h (critical) / 72h (standard) | 48h (critical) / 1 semana (standard) | sales-chief → c-level-chief |
| Data Squad | 72h | 1 semana | sales-chief → data-chief |
| Movement Squad | 72h | 1 semana | sales-chief → movement-chief |
| Advisory Squad | 72h | 72h | sales-chief → advisory-chief |

## SLAs de Rework

| Tipo de Rework | SLA por Ciclo | Max Ciclos | Escalation |
|---------------|--------------|------------|------------|
| Audit rework | 8h | 3 | sales-chief decide: aprovar com notas OU reassignar |
| Coaching rework | 24h | 2 | sales-chief + c_level_squad |
| Scoring calibration | 4h | 1 | sales-chief convoca calibration session |

## SLAs de Escalation

| Severidade | SLA de Resposta | Respondido Por |
|-----------|----------------|----------------|
| Critical (closer score < 40, deal risk critical) | Mesmo dia | sales-chief |
| High (quality gate fail 3x, expert divergence) | 24h | sales-chief / qa-guardian |
| Medium (scoring variance, minor gaps) | 48h | qa-guardian |
| Low (process improvement, documentation) | 1 semana | Agente owner |

## Monitoramento

- **Registro de SLA**: Toda violação de SLA registrada em `data/decisions/decisions-registry.yaml`
- **Review semanal**: SLA compliance revisada na `weekly-sales-quality-review`
- **Métrica**: SLA compliance rate target ≥ 95%
- **Dashboard**: `data/metrics/sla-compliance-metrics.yaml` (quando disponível)
